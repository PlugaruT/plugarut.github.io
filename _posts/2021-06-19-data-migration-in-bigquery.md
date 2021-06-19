---
title: Schema changes and data migration in BigQuery
layout: post
projects: false
category: blog
author: tudor
externalLink: false
---
A few months ago, I had to perform data migration in BigQuery. I hope that you already know what is BigQuery, if not, google it. It’s a nice tool provided by Google if you want to store huge amounts of data at a low cost. 

At the first sight, it does not sound too difficult and I immediately started to write a SQL query that would just read from one table and store the data in another table. Hey, what can be difficult in this 🤷 The trick was that the new table, had a slightly different schema, and the original data needed to be changed a bit to “fit” in the new table. 

Inside BigQuery tables, you can store nested data, it supports having columns of type `RECORD`, it’s something like a table inside another table. And they went the extra mile and made BigQuery support arrays of `RECORD`s, pretty neat if you ask me.

So, back to the problem. In my case, in the old table, one of the columns from a `RECORD` was of type `STRING` but in the new one, it was of type `INT64`. So, I had to cast that column first, before being able to store it nicely in the new table. 
Let’s say you have a table named order with the following schema:
```JSON
[
  {
    "name": "id",
    "type": "INTEGER"
  },
  {
    "name": "store",
    "type": "STRING"
  },
  {
    "name": "lines",
    "type": "record",
    "mode": "repeated",
    "fields": [
      {
        "name": "id",
        "type": "INTEGER"
      },
      {
        "name": "item",
        "type": "STRING"
      },
      {
        "name": "qty",
        "type": "STRING"
      }
    ]
  }
]
```
You can see the column `lines` which are of type `RECORD` and it’s also `REPEATED`, meaning it’s a list of records.
So, in my case, the column `qty` from `lines` record, in the new table was of type `INT64`, but you can see in the old one is of type `STRING`. How do we reach that column with SQL and cast that column?
We need to use `REPLACE` to first unnest the `RECORD`, then convert it to an `ARRAY` and perform the casting. The SQL query looks like this:
```SQL
SELECT * REPLACE(
    ARRAY(
        SELECT AS STRUCT l_items.* EXCEPT(qty)
        FROM UNNEST(lines) as l_items 
    ) as lines,
)
FROM `project_id.dataset_id.order`
```
In the query above, I used the `EXEPT` operation to not include that column at all in the result, so that the new table to have that column empty. This worked fine in my case since because of the wrong type, there was no data, and was no point in casting the column at all. But, if you need cast is, you just need to replace the EXCEPT part, with the proper SQL operation.

So, what if you have to cast a column from a list of records inside another list of records and so on? You just use the same technique and apply recursion to do this. And of course, I had this situation and I had to write this recursive SQL to exclude a column, but hey, nothing it’s easy in this life... It took me around 3 hours to write to SQL, cause' I'm not the most skilled in SQL, but, I got the job done 💪.

That’s it, folks!
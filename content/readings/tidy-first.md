---
title: Tidy First? by Kent Beck
date: 2024-01-12
---
![](https://m.media-amazon.com/images/I/81aFdV9iDQL._SY160.jpg)

### Metadata

- Author: Kent Beck
- Full Title: Tidy First?
- Category: #books

### Highlights

>  Coupling and cohesion are simply measures of the complexity of computer code, not from the perspective of the computers executing the programs but that of human beings trying to understand the code.

> Coupling and cohesion are really all about how your brain deals with complicated systems.

> Software design is a powerful tool to ease pain in the world—​if it is used well. Used badly, it becomes just another instrument of oppression, and a drag on the effectiveness of software development.

> Software design creates value, when it creates value, that is realized over time.
 
> The world is challenging enough that we can’t afford to ignore opportunities to make things easier for ourselves and others.

> Tidyings are a subset of refactorings. Tidyings are the cute, fuzzy little refactorings that nobody could possibly hate on.

> “Refactoring” took fatal damage when folks started using it to refer to long pauses in feature development. 

> Creating a pass-through interface is the micro-scale essence of software design. You want to make some behavior change. 

> Reorder the code in the file in the order in which a reader (remember, there are many readers for each writer) would prefer to encounter it. 

> As always, separate the tidying commit from the behavior change commit.

> You see a block of code inside a routine that has an obvious purpose and limited interaction with the rest of the code in the routine. Extract it as a helper routine. Name the routine after the purpose (not how the routine works).

> The biggest cost of code is the cost of reading and understanding it, not the cost of writing it. 

> When you see a comment that says exactly what the code says, remove it. 

> The tidyings have to go somewhere, or you don’t tidy. Where do they go? Summary: they go in their own PRs, with as few tidyings per PR as possible. 

> Once you get comfortable with tidying, with working in small steps, with working with absolute safety, I encourage you to experiment with not requiring reviews for tidying PRs. This reduces latency further, incentivizing even smaller tidying PRs. 

> You and your team are going to need to figure out how exactly to reduce the cost of review. In teams with trust and a strong culture, tidyings don’t require review. The risk of interactions has been reduced so far that unreviewed tidying doesn’t destabilize the software. 

> More than an hour of tidying at a time before making a behavior change likely means you’ve lost track of the minimum set of structure changes needed to enable your desired behavior change. 

> Tidying is a great way to become aware of the detailed consequences of your design. Tidying illuminates the design as it could be. 

> Sometimes I just don’t have the energy to tackle a new feature, but I want to work. Picking an item off the Fun List and tidying it brings me joy. Don’t underestimate how much better you are as a programmer when you’re happy. 

> If waiting to tidy at a later date substantially increases the cost of tidying, consider doing it now.

> In general, bias toward tidying first, but be wary of tidying becoming an end in itself. 

> Understanding theory optimizes application.

> Understanding theory sharpens your judgment for when you have to answer these questions on speculation. Understanding theory lets you disagree constructively with your fellow geeks. 

> Software creates value in two ways: What it does today The possibility of new things we can make it do tomorrow 

> Behavior creates value. 

> The structure of the system doesn’t matter to its behavior. One big function, a whole bunch of itty bitties, same paycheck comes out. The structure creates options. The structure could make it easy to add new countries to our paycheck calculation, or it could make it hard. 

> structure changes and behavior changes are both ways to create value, but that they are fundamentally different. 

> The more uncertain my predictions of value are, the greater the value of the option is 

> Software design is preparation for change; change of behavior. 

> Design we do today is the premium we pay for the “option” of “buying” the behavior change tomorrow. 

> The more volatile the value of a potential behavior change, the better. 

> The less design work I could do to create an option, the better. 

> One property relevant to tidying first is that structure changes are generally reversible. 

> I learned the value of reversibility (long before I had a name for it) and realized the value of making decisions reversible. 

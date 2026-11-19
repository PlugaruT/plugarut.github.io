# frozen_string_literal: true

source "https://rubygems.org"

# Built and deployed by GitHub Actions (.github/workflows/pages.yml),
# so we can use Jekyll 4 instead of the github-pages gem.
gem "jekyll", "~> 4.4"

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.18"
  gem "jekyll-sitemap", "~> 1.4"
  gem "jekyll-seo-tag", "~> 2.9"
end

# For local development (`jekyll serve` on Ruby 3+)
gem "webrick", "~> 1.9"

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
gem "tzinfo-data", platforms: [:windows, :jruby]

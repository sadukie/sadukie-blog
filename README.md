Since including the Gemfile makes the workflow cranky, I've added it to .gitignore.

These are the contents of my latest Gemfile for the dev container:

```ruby
source "https://rubygems.org"

gem 'github-pages', group: :jekyll_plugins
gem 'jekyll-feed'
```
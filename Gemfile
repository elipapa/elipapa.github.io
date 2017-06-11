source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']
gem 'rb-gsl'
gem 'narray'
gem 'jekyll-paginate'
gem 'html-proofer'

group :jekyll_plugins do
  gem 'jekyll-compose'
end

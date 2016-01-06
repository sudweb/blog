source 'https://rubygems.org'

require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)

gem 'github-pages', versions['github-pages']

group :development do
  gem 'foreman', '~> 0.78.0'
  gem 'therubyracer'
end

group :test do
  gem 'rake'
  gem 'jekyll', versions['jekyll']
  gem 'html-proofer'
  gem 'mdl', '~> 0.2.0'
end

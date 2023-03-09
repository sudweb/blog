# frozen_string_literal: true

source 'https://rubygems.org'
ruby '2.6.3'

gem 'jekyll', '~>3.8.5'
gem 'liquid', :git => 'https://github.com/Shopify/liquid.git', branch: 'master'
gem 'sassc'

group :jekyll_plugins do
  gem 'jekyll-github-metadata'
  gem 'jekyll-microtypo'
  gem 'jekyll-redirect-from'
  gem 'jekyll-sitemap'
  gem 'liquid-md5'
  gem 'jekyll-paginate-v2', '~> 1.8', '>= 1.8.1'
  gem 'octopress-autoprefixer'
  gem 'jekyll-include-cache'
end

group :development do
  gem 'foreman'
  # gem 'jekyll-livereload'
end

group :test do
  gem 'html-proofer', '~> 3.4'
  gem 'rake', '~> 12.0'
end

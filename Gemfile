source "https://rubygems.org"

branch = ENV.fetch('SOLIDUS_BRANCH', 'master')
gem "solidus", github: "solidusio/solidus", branch: branch
gem 'solidus_auth_devise'
gem 'deface'

if branch == 'master' || branch >= "v2.3"
  gem 'rails', '~> 5.1.0' # hack for broken bundler dependency resolution
elsif branch >= "v2.0"
  gem 'rails', '~> 5.0.0' # hack for broken bundler dependency resolution
else
  gem "rails", "~> 4.2.7"
end

if ENV['DB'] == 'mysql'
  gem 'mysql2', '~> 0.4.10'
else
  gem 'pg', '~> 0.21'
end

group :development, :test do
  gem "pry-rails"
end

group :test do
  gem 'rails-controller-testing'
  if branch < "v2.5"
    gem 'factory_bot', '4.10.0'
  else
    gem 'factory_bot', '> 4.10.0'
  end
end

gemspec

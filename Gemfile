# frozen_string_literal: true

source "https://rubygems.org"

gem 'selenium-webdriver'
branch = ENV.fetch('SOLIDUS_BRANCH', 'master')
gem "solidus", github: "solidusio/solidus", branch: branch

group :test do
  if branch == 'master' || branch >= "v2.0"
    gem 'rails-controller-testing', '~> 1.0'
  else
    gem "rails_test_params_backport"
  end

  gem 'factory_bot', (branch < 'v2.5' ? '4.10.0' : '> 4.10.0')
end

if ENV['DB'] == 'mysql'
  gem 'mysql2', '~> 0.4.10'
else
  gem 'pg', '~> 0.21'
end

group :development, :test do
  gem 'pry-rails', '~> 0.3.9'
end

gemspec

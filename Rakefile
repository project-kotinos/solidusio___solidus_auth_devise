# frozen_string_literal: true

require 'bundler'
Bundler::GemHelper.install_tasks
require 'yourbase/rspec/skipper'
require 'rspec/core/rake_task'
require 'spree/testing_support/common_rake'

RSpec::Core::RakeTask.new

task :default do
  Rake::Task[:test_app].invoke
  Dir.chdir("../../")
  Rake::Task[:spec].invoke
end

desc 'Generates a dummy app for testing'
task :test_app do
  ENV['LIB_NAME'] = 'solidus/auth'
  Rake::Task['common:test_app'].invoke("Spree::User")
end

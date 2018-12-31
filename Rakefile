require "bundler/gem_tasks"
require "rspec/core/rake_task"
require 'spree/testing_support/extension_rake'

RSpec::Core::RakeTask.new(:spec)

task :default do
  if Dir["spec/dummy"].empty?
    Rake::Task[:test_app].invoke
    Dir.chdir("../../")
  end
  Rake::Task[:spec].invoke
end

desc 'Generates a dummy app for testing'
task :test_app do
  ENV['LIB_NAME'] = 'super_good/solidus_taxjar'
  Rake::Task['extension:test_app'].invoke
end

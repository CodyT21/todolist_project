require "rake/testtask"
require 'find'
require 'bundler/gem_tasks'


desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'Display program files'
task :files do
  # Find.find(File.absolute_path('.')) do |path|
    # name = File.basename(path)
  Find.find('.') do |path|
    if path.include?('/.')
      Find.prune unless File.file?(path)
      next
    else
      puts path if File.file?(path)
    end
  end
end


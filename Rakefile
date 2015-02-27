%w[rubygems rake rake/clean rake/testtask fileutils].each { |f| require f }
require File.dirname(__FILE__) + '/lib/restful_query'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |s|
    s.name = %q{restful_query}
    s.version = RestfulQuery::VERSION
    s.authors = ["Aaron Quint"]
    s.email = "aaron@quirkey.com"
    s.homepage = "https://github.com/quirkey/restful_query"
    s.license = "MIT"
    s.summary = 'Simple ActiveRecord and Sequel queries from a RESTful and safe interface'
    s.description   = %q{RestfulQuery provides a simple interface in front of a complex parser to parse specially formatted query hashes into complex SQL queries. It includes ActiveRecord and Sequel extensions.}
  end
  Jeweler::RubygemsDotOrgTasks.new
  
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

Rake::TestTask.new do |t|
  t.libs << "test"
  t.test_files = FileList["test/**/*_test.rb"]
  t.verbose = true
end

Dir['tasks/**/*.rake'].each { |t| load t }

task :default => :test

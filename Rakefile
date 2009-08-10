%w[rubygems rake rake/clean hoe fileutils newgem rubigen].each { |f| require f }
require File.dirname(__FILE__) + '/lib/restful_query'

# Generate all the Rake tasks
# Run 'rake -T' to see list of generated tasks (from gem root directory)
$hoe = Hoe.spec('restful_query') do |p|
  p.version = RestfulQuery::VERSION
  p.developer('Aaron Quint', 'aaron@quirkey.com')
  p.changes              = p.paragraphs_of("History.txt", 0..1).join("\n\n")
  p.rubyforge_name       = 'quirkey'
  p.description = p.summary = 'Simple ActiveRecord and Sequel queries from a RESTful and safe interface'
  p.url                  = 'http://code.quirkey.com/restful_query'
  p.extra_deps         = [
    ['activesupport','>= 2.2.0'],
    ['activerecord','>= 2.2.0'],
    ['chronic','>= 0.2.3']
  ]
  p.extra_dev_deps = [
    ['newgem', ">= #{::Newgem::VERSION}"],
    ['Shoulda', '>= 1.2.0']
  ]
  
  p.clean_globs |= %w[**/.DS_Store tmp *.log]
  path = (p.rubyforge_name == p.name) ? p.rubyforge_name : "\#{p.rubyforge_name}/\#{p.name}"
  p.remote_rdoc_dir = File.join(path.gsub(/^#{p.rubyforge_name}\/?/,''), 'rdoc')
  p.rsync_args = '-av --delete --ignore-errors'
end

require 'newgem/tasks' # load /tasks/*.rake
Dir['tasks/**/*.rake'].each { |t| load t }

# TODO - want other tests/tasks run by default? Add them to the list
# task :default => [:spec, :features]

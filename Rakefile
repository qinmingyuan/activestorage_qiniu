begin
  require 'bundler/setup'
rescue LoadError
  puts 'You must `gem install bundler` and `bundle install` to run rake tasks'
end

require 'sdoc'
require 'rdoc/task'

RDoc::Task.new(:sdoc) do |rdoc|
  rdoc.rdoc_dir = 'docs'
  rdoc.title = 'QiniuRails'
  rdoc.options << '--format=sdoc'
  rdoc.template = 'rails'
  rdoc.rdoc_files.include('README.md')
  rdoc.rdoc_files.include('app/**/*.rb')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

APP_RAKEFILE = File.expand_path('test/dummy/Rakefile', __dir__)
load 'rails/tasks/engine.rake'
load 'rails/tasks/statistics.rake'

require 'bundler/gem_tasks'
require 'rake/testtask'

Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.libs << 'test'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = false
end


task default: :test

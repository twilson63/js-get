require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "js-get"
    gem.summary = %Q{cli javascript library install}
    gem.description = %Q{command line interface to install js libraries}
    gem.email = "tom@jackhq.com"
    gem.homepage = "http://github.com/twilson63/js-get"
    gem.authors = ["Tom Wilson"]
    gem.add_development_dependency "thoughtbot-shoulda", ">= 0"
    gem.add_dependency('rest-client', '>= 1.0.3')
    gem.add_dependency('crack', '>= 0.1.2')
    gem.has_rdoc = true
    
    
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: sudo gem install jeweler"
end

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

begin
  require 'rcov/rcovtask'
  Rcov::RcovTask.new do |test|
    test.libs << 'test'
    test.pattern = 'test/**/test_*.rb'
    test.verbose = true
  end
rescue LoadError
  task :rcov do
    abort "RCov is not available. In order to run rcov, you must: sudo gem install spicycode-rcov"
  end
end

task :test => :check_dependencies

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "js-get #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('bin/js-get')
end

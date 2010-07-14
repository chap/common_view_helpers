require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "common_view_helpers"
    gem.summary = %Q{Common view helpers for Rails apps}
    gem.description = %Q{Common view helpers used by Gemini in most of our applications}
    gem.email = "admin@geminisbs.com"
    gem.homepage = "http://github.com/geminisbs/common_view_helpers"
    gem.authors = ["Zeke Sikelianos", "Mauricio Gomes"]
		gem.add_dependency "activesupport", ">= 2.0.0"
		gem.add_development_dependency "rspec", ">= 1.2.9"
		gem.add_development_dependency "RedCloth", ">= 4.1.0"
		gem.files = FileList['lib/**/*.rb', 'init.rb', 'rails/**/*.rb', 'VERSION', 'LICENSE', "README.rdoc"]
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "common_view_helpers #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

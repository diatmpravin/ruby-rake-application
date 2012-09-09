# 
# To change this template, choose Tools | Templates
# and open the template in the editor.
 

require 'rubygems'
require 'rake'
require 'rake/clean'
require 'rake/gempackagetask'
require 'rake/rdoctask'
require 'rake/testtask'

#TEST TASK
task :test do
  puts "Hello World!"
end

#TASK DEPENDENCIES
task :build => [:generate_html, :copy_images]
task :generate_html => [:create_directories]
task :copy_images => [:create_directories]
task :create_directories do
  puts 'thanks'
end

#TASK ACTION
task :task_action => [:generate_file]

task :generate_file do
  system %{./runwpb rake.wpb}
end

# TASK ACTION AND DEPENDENCIES
task :a => [:b, :c] do
 puts "a"
end

task :b => [:d]     do
 puts "b"
end

task :c => [:d]     do
 puts "c" 
end

task :d             do
 puts "d"
end


spec = Gem::Specification.new do |s|
  s.name = 'scrap-coach_details'
  s.version = '0.0.1'
  s.has_rdoc = true
  s.extra_rdoc_files = ['README', 'LICENSE']
  s.summary = 'Your summary here'
  s.description = s.summary
  s.author = ''
  s.email = ''
  # s.executables = ['your_executable_here']
  s.files = %w(LICENSE README Rakefile) + Dir.glob("{bin,lib,spec}/**/*")
  s.require_path = "lib"
  s.bindir = "bin"
end

Rake::GemPackageTask.new(spec) do |p|
  p.gem_spec = spec
  p.need_tar = true
  p.need_zip = true
end

Rake::RDocTask.new do |rdoc|
  files =['README', 'LICENSE', 'lib/**/*.rb']
  rdoc.rdoc_files.add(files)
  rdoc.main = "README" # page to start on
  rdoc.title = "scrap-coach_details Docs"
  rdoc.rdoc_dir = 'doc/rdoc' # rdoc output folder
  rdoc.options << '--line-numbers'
end

Rake::TestTask.new do |t|
  t.test_files = FileList['test/**/*.rb']
end

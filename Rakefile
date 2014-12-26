require 'haml'

SOURCE_DIR = "source"
BUILD_DIR = "build"
BACKGROUND_IMAGE = "background.jpg"

TRACE = ARGV.include?("--trace") && "--trace" || ''

task :default => :hamlize do
  #Rake::Task['hamlize'].invoke
end

task :hamlize => [:clean, :build_dir, :build_background ] do
  env_year = "#{Time.now.year}"
  source = "#{SOURCE_DIR}/tombola.haml"
  build = "#{BUILD_DIR}/tombola.html"
  system "haml #{TRACE} #{source} #{build}"
end

task :build_scripts => :build_dir do
  source = "#{SOURCE_DIR}/table.coffee"
  build = "#{BUILD_DIR}/table.js"
  system "rm #{build}" if File.exist? build
  system "sprockets --noenv -I#{SOURCE_DIR} #{source} > #{build}"
end

task :build_background do
  source = "#{SOURCE_DIR}/#{BACKGROUND_IMAGE}"
  build = "#{BUILD_DIR}/#{BACKGROUND_IMAGE}"
  system "cp #{source} #{build}"
end

task :build_dir => :clean do
  system "mkdir #{BUILD_DIR}"
end

desc "Clean build files"
task :clean do
  system "rm -f #{BUILD_DIR}/*; rmdir #{BUILD_DIR}" if File.exist? BUILD_DIR
end
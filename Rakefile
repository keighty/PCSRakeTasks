require "rubygems"
require 'rake'

desc "greet the user"
task :greet do
  puts "hello world!"
end

desc "make a new notes file"
task :post do
  title = ENV["title"] || "new-post"
  slug = title.downcase.strip.gsub(' ', '_').gsub(/[^\w-]/, '')
  begin
    date = (ENV['date'] ?
      Time.parse(ENV['date']) : Time.now).strftime('%y%m%d')
  end
  filename = File.join("./", "#{date}_#{slug}.md")
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end

  puts "Creating new post: #{filename}"
  open(filename, 'w') do |post|
    post.puts "# #{title.gsub(/-/,' ').capitalize}"
  end
end # task :post

desc "make a spec testing env"
# usage rake test project="bob"
task :project do
  title = ENV["title"] || "new-project"
  Dir.mkdir(title)
  Dir.chdir(title)
  Dir.mkdir("test")
  Dir.mkdir("lib")
  filename = "#{title}.rb"
  File.new("lib/#{filename}", "w")
  File.new("test/test_#{filename}", "w")

  open("test/test_#{filename}", "w") do |spec|
    spec.puts "require 'minitest/autorun'"
    spec.puts "require_relative '../lib/#{filename}'"
  end
end
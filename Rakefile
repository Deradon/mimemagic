require 'rake/testtask'

task :default => %w(test)

desc 'Run tests with minitest'
Rake::TestTask.new do |t|
  t.libs << 'test'
  t.pattern = 'test/*_test.rb'
end

desc 'Generate mime tables'
task :tables do
  if ENV["RELEASE"]
    source_url = "https://gitlab.freedesktop.org/xdg/shared-mime-info/-/raw/#{ENV['RELEASE']}/data/freedesktop.org.xml.in"
    sh "script/generate-mime.rb '#{source_url}' > lib/mimemagic/tables.rb"
  else
    sh "script/generate-mime.rb > lib/mimemagic/tables.rb"
  end
end

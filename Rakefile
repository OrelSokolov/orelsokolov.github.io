require 'erb'
require 'yaml'
require 'pry'

class Hash
  def method_missing(name, *args)
    send(:[], name.to_s, *args)
  end
end

task :build do
  erb_file = 'index.html.erb'
  html_file = File.basename(erb_file, '.erb') #=>"page.html"

  erb_str = File.read(erb_file)

  renderer = ERB.new(erb_str)
  result = renderer.result()

  File.open(html_file, 'w') do |f|
    f.write(result)
  end
end
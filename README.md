# BasicRailsGem
You Are going to create your own ruby gem and publish it in RubyGems.org

Let's Do IT

create a directory "lib",

add new file "<gem_file_name>.rb" into the created "lib" folder

inside it:

class <gem_class_name>
  //your code here
end


#Example: I have created first_gem.rb file

class FirstGem
  def self.is_working?
    puts "Print here"
  end
end

Now, in your root directory (in where you created lib folder) 
create one file "<gem_file_name.gemspec>" and add specifications in it.

for example:

Gem::Specification.new do |s|
  s.name        = 'FirstGem'
  s.version     = '0.0.0'
  s.date        = '2019-09-09'
  s.summary     = "Hola!"
  s.description = "creating a simple gem"
  s.authors     = ["Nick Quaranto"]
  s.email       = 'nick@quaran.to'
  s.files       = ["lib/first_gem.rb"]
  s.homepage    =
    'https://rubygems.org/gems/first_gem_515'
  s.license       = 'MIT'
end

Done. It's time to build it

gem build <gemspec_file>     //gem build first_gem.gemspec

it will create a file with extension ".gem"

you can install it locally by " gem install file_name.gem"     //gem install FirstGem515-0.0.0.gem

Checking Locally:

//irb
>> require 'first_gem'
=> true
>> FirstGem.is_working?
Yes It's Working!
=> nil

Publilsh:

curl -u <user_name> https://rubygems.org/api/v1/api_key.yaml > ~/.gem/credentials; chmod 0600 ~/.gem/credentials 

Enter host password for user 'user_name':

then, "gem push <file_name>.gem"  //gem push FirstGem515-0.0.0.gem

--Completed publishing your first gem--

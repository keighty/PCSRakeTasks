#Automate Tasks with Rake

Make is a utility that automatically builds executable programs and libraries from source code by reading files called makefiles which specify how to derive the target program. [Wikipedia](http://en.wikipedia.org/wiki/Make_(software))

`Rake` stands for Ruby-make

1. Download and install rake with the following.
```
$ gem install rake
```

2. Write your tasks into a "Rakefile"
```
task :greet do
  puts "Hello World"
end
```

3. Run your task at the command line
```
$ rake greet
Hello World!
```

4. Celebrate with a placekitten:

![placekitten.com(http://placekitten.com/g/200/300)](http://placekitten.com/g/200/300)
---
layout: post
title:  "How I Learn a New Language"
date:   2016-09-11 10:42:51 +0100
categories: apprenticeship
---

![photo inside train]({{ site.url }}/assets/train.jpg)
If learning new languages is part of your job then it's really important to be
efficient with then as soon as possible.
That's why I use a pattern that helps me to learn a new language and I can apply it
to any one.

Here is the list of what I want to know 

- Core of the language
- Syntax
- Framework
- Tools
- Continuous Integration


As I am currently learning Ruby, I thought it best to share how I am applying
my pattern to this language.
I find that it is always a good idea to have a puppet project when you learn
a new language so that you are getting practical experience.

## Core and Syntax
Ruby is an interpreted language. To truly understand it will help a crafter to
know how to write efficient and secure code.
To do this I'm currently reading the book *The Well-Grounded Rubist*, and plan to
read Eloquent Ruby.

Here is a example of how dependancy really works with Ruby.
{% highlight ruby linenos %}
moduel MyModule
  def example
    puts "it's an example"
  end
end

class MyClass
  include MyModule
end

class AnotherClass < MyClass
end

obj = AnotherClass.new
obj.example
{% endhighlight %}

when the interpreter will run obj.example I know that it will search the method
in AnotherClass, MyClass and finally into MyModule. It's also why a crafter would avoid
to write a spagethi code with loads of inheritance. A crafter will also want to understand
the difference between **include** MyModule or **prepend** MyModule when they implement a module.

This knowledge will enable a crafter to read open source projects and write a project.
It is also a great way to learn the syntax.

## Framework and Library
In general, the first and only Framework that I'm looking for is the testing.
How to pick up which framework is pretty easy, just ask which one your
coworker uses. I'm using RSpec, which is set up on the project.

Then I will learn which frameworks are the most popular for Ruby. 
I have found the two most popular are:

- [Ruby on Rails](https://github.com/rails/rails)
- [Sinatra](https://github.com/rails/rails)

I don't need to learn how to use them at the start as I want to stay focused on Ruby.
At best, I will read their code and I will be more knowledgable.

I will also make myself comfortable to use the libraray and application package management.
These commands are enough so far:

{% highlight ruby %}
gem install a_lib
gem list
gem uninstall a_lib
{% endhighlight %}

[Documentation Gem](http://guides.rubygems.org/rubygems-basics/)

## Tools
So far I still don't search my tools.
But it can be extansion for Vim, that I use and tools that I need for debuggign

I will use the command irb
and ruby -h

{% highlight ruby %}
#it check the synthax without runnign the code
ruby -cw my_file.rb

#dipalay the version with ex of code, can be usefull when ask for help
ruby -ve my_file.rb
{% endhighlight %}

## Continuous Integration
For each project I want to be able to set my continuous integration.
Also the tools depend of what the company use, by default I will use
TravisCI with coverall or something like CodeCov.

This will make me more confortable with like:

- [Rake](http://rake.rubyforge.org/) - task-management
- [Gemfile](http://bundler.io/gemfile.html) - dependence-management

## Conclusion
The purpose isn't to know everything, but is to really know well the basic and
the more you use it understand it well

If you have any sugestion, I really want to hear about it!

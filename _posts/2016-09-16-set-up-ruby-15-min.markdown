---
layout: post
title:  "Set Up Your Ruby Env. in 15 minutes"
date:   2016-09-16 10:42:51 +0100
categories: apprenticeship
---

![rain in london]({{ site.url }}/assets/rain.jpg)
I will explain step by step how to set up a continuous integration environment for Ruby.
Then how to make it in 1 seconde with a script.

At minimum, you will need an account on each one of these websites:

- [Github](https://github.com)
- [Travis](https://travis-ci.org)
- [CoverAlls](https://coveralls.io)

First we create our configuration files.
{% highlight shell %}
mkdir my_ruby_project
cd my_ruby_project
touch Gemfile
touch Rakefile
touch .travis.yml
{% endhighlight %}

Here is the content of our Gemfile. The file manages our external dependencies and is composed of:

- Rake: a Ruby build program and it will be used by Travis.
- RSpec: our test framework.
- Coveralls: a dependancy needed by Coveralls.
{% highlight ruby %}
source "https://rubygems.org"

gem 'rake'
gem 'rspec', '~> 3.0'
gem 'coveralls', require: false
{% endhighlight %}

This is the content of the Rakefile. Travis will execute it each time you commit your code on
Github. This will make Travis launch all of your tests.
{% highlight ruby %}
require 'rake'
require 'rspec/core/rake_task'

RSpec::Core::RakeTask.new(:spec) do |t|
end

task :default => :spec
{% endhighlight %}

The last configuration file for *.travis.yml* - This file will tell travis what environment you
want your code to be compiled and tested.
{% highlight ruby %}
language: ruby
rvm:
- 2.3.0
script:
- bundle exec rspec
{% endhighlight %}

Now our configuration files are ready, we can install our package by executing these three command lines.
The first one will install the package *Bundle* if you don't have it. The second line will install our
dependancy with our new package *Bundle* using our Gemfile. Finally, the last line will set up
our test environment.

{% highlight shell linenos %}
Gem install bundle
bundle install --binstubs
bin/rspec --init
{% endhighlight %}

It is nearlly done. Now we just have to add these two lines at the top of our spec/spec_helper.rb file.
{% highlight ruby %}
require 'coveralls'
overalls.wear!
{% endhighlight %}

And finally call our spec/spec_helper into all of our future test files!
{% highlight ruby %}
require 'spec_helper'
{% endhighlight %}

Now that you will have written your tests and code, *rspec* will let you launch your tests locally.

Now you can download my Bash script and it will execute all these steps for you!
[bash file to set up in 1 second](https://github.com/fabientownsend/setup_ruby/blob/master/setup_ruby.sh)
Do not forget to activate your Travis/Coveralls access to your Github.

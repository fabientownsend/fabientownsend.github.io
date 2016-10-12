---
layout: post
title:  "Create A Ruby Package 1/2"
date:   2016-10-12 10:42:51 +0100
categories: apprenticeship
---

![notes for my packaging]({{ site.url }}/assets/notes.jpg)
In my previous post, I shared the first resources that I found to help me
with my task. Today, I will explain how I created my Rugy Gem.

## Create And Configurate A Basic Gem
I could create my gem as it's very well explained on rubygems.org:
[make you own gem](http://guides.rubygems.org/make-your-own-gem/) but, instead,
I will use a bundler's build gem skeleton to create a basic gem to save some time.

Well, not that basic, it also create a basic test and configurate it for travis
and that, is cool!

For that, if it's not the case, I need to Install [bundler](https://rubygems.org)

{% highlight ruby %}
$ gem install bunbler
{% endhighlight %}

Bundler installed, let's use its gem builder:

{% highlight ruby %}
$ bundle gem gem_name
{% endhighlight %}

And it's done! Let's add CoverAlls now, in my Gemfiles I will ask to install
those three gem:

{% highlight ruby %}
source 'https://rubygems.org'

# Specify your gem's dependencies in core_tic_tac_toe.gemspec
gem 'rake'
gem 'rspec', '~> 3.0'
gem 'coveralls', require: false
gemspec
{% endhighlight %}

add those two line to the *spec/spec_helper.rb*

{% highlight ruby %}
require 'coveralls'
Coveralls.wear!
{% endhighlight %}

Now it's done with my basic gem all configured and ready to receive the code
and its test from my Tic-Tac-Toe project.

You can find my Gem repository [here](https://github.com/fabientownsend/ruby-core-tic-tac-toe)

# Use A Gem From A Github Repository

No that I created my Gem, I want to use use it in my other project.
Let's update the Gemfile of my [command line project](https://github.com/fabientownsend/ruby-cli-tic-tac-toe)

{% highlight ruby %}
source "https://rubygems.org"

gem 'rake'
gem 'core_tic_tac_toe', :git => 'https://github.com/fabientownsend/ruby-core-tic-tac-toe'
gem 'rspec', '~> 3.0'
gem 'coveralls', require: false
{% endhighlight %}

When I execute *bundle install* it will download and install my gem.
This one will be installed in the INSTALLATION_DIRECTORY, you can find where this
directory is with the command *gem environment*.

Now I can use all the class present in the lib folder of my gem.
One more thing, from now, for running my project or its tests I need to prepocess
my commands with *bunbler exec*. For example, *bundler exec rspec*.

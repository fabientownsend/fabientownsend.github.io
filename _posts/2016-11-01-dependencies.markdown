---
layout: post
title:  "Dependencies"
date:   2016-11-01 10:42:51 +0100
categories: apprenticeship
---
![practical object-oriented design in ruby cover]({{ site.url }}/assets/oop.jpg)
I have just finished reading about dependencies in the book *Practical
Object-Oriented Design in Ruby*, which is why I have decided to write an article
about it. Hopefully, writing an article will help me to improve my understanding
and apply this new knowledge to my project in order to make it easier to modify.

Each coupling creates a dependency. The more a class knows about other classes,
the more intertwined they become. This will make it more time consuming and
more complicated to implement new functionality in a software.

The first step is to be able to detect them. Here are some examples of
dependencies:

- Class(es) created inside a class.
- The number and order of the arguments for the class initialisation.

When you find dependencies, you can work towards losing this coupling by
abstracting them.

**Class(es) created inside a class**

In this case, instead, we can inject the class during its initialisation. The
injected class can be changed and this will not affect our class. Note that
the class injected should respect the same interface.

{% highlight ruby %}
# before
class Game
  def initialize(player_one, player_two)
    @player_one = player_one
    @player_two = player_two
    @board = Board.new
  end
end

# after
class Game
  def initialize(player_one, player_two, board)
    @player_one = player_one
    @player_two = player_two
    @board = board
  end
end
{% endhighlight %}

example of code

**The order of the arguments for the class creation**

We can easily get rid of the order and number of the arguments dependency by
using a hash as an argument. This way, the number and order of arguments can 
change and it will not break any of the classes.

{% highlight ruby %}
# before
class GameBuilder
  def initialize(board_size, game_type, first_player)
    @board_size = board_size
    @game_types = game_type
    @first_player = first_player
  end
end

# after
class GameBuilder
  def initialize(args)
    @board_size = args[:board_size]
    @game_types = args[:game_types]
    @first_player = args[:first_player]
  end

  def defaults
    {:board_size => 3, :game_type => 0, :first_player => 0}
  end
end
{% endhighlight %}

If I was to remember one thing from this article it would be this sentence:
*depend on things that change less often than they do*

---
layout: post
title:  "Exception as Control Flow: A Good Practice?"
date:   2016-09-23 10:42:51 +0100
categories: apprenticeship
---

![git pull request]({{ site.url }}/assets/control_flow.jpg)
The control flow evaluates an input statement in order to determine the
output. It can be managed through exception or if/else evaluations.

Exception as control flow is said to be an AntiPattern:

> An AntiPattern is a literary form that describes a commonly occuring
> solution to a problem that generates decidedly negative consequences.

We can split this problem into two parts:

- Readability
- Computering

# Readibility
Example 1:

{% highlight ruby %}
def play_move
  position = @current_player.next_move

  begin
    board.set_mark(@current_player.mark, position)
  rescue OccupiedPositionError
    ui.occupied_position
    play_move
  rescue OutOfRangeError
    ui.between(board.POSITION_MIN, board.POSITION_MAX - 1)
    play_move
  rescue ArgumentError
    ui.must_be_integer
    play_move
  end
end
{% endhighlight %}

Example 2:
{% highlight ruby %}
def play_move
  position = @current_player.next_move

  if position > board.POSITION_MAX - 1 || position < board.POSITION_MIN
    ui.between(board.POSITION_MIN, board.POSITION_MAX - 1)
    play_move
  elsif !@board.free_positions.include?(position)
    ui.occupied_position
    play_move
  else
    board.set_mark(@current_player.mark, position)
  end
end
{% endhighlight %}

We can't tell if one code is more readable than the other.

The main difference is in the first example, my **class Board tells** me that
it doesn't accept some conditions and the second example, **I ask**
my class if I respect the conditions.

When does it seem legitimate to *tell* or to *ask*?

The most obvious situation where you need to tell or even yield, is when the user
of your method can't have access to your code and you need to tell them
that they misused your method.

When the developer can have access to the code and its tests, you don't need
exception. The developer has all of the information needed to make the
verification of the correct input before using your method.

# Perfomance
Unfortunately, I don't have much experience with this yet.

According to *the internet*, the performance of Exception is pretty bad.
> Exception should not be part of the regular flow.

This seems to be the case for different languages:
- [.Net](http://stackoverflow.com/questions/161942/how-slow-are-net-exceptions)
- [Java](http://stackoverflow.com/questions/299068/how-slow-are-java-exceptions)
- [Ruby](https://simonecarletti.com/blog/2010/01/how-slow-are-ruby-exceptions/)

## Conclusion
I decided to remove exception as control flow from my project.
A side effect of this decision is that I feel like I removed
some conditions from my class Board that say *"hey, don't use my method with that"*.

With Java or C#, I would have chose the second solution with these assertions
into my class Board. During the compilation of the project, these assertions
would be removed,  but with Ruby I don't know how to do it or even if it's possible.

Example assertion:
{% highlight ruby %}
def set_mark(mark, position)
  assert(!is_free?(position)
  assert(!position < POSITION_MAX - 1)
  assert(!position > POSITION_MIN)
  assert(position != Integer)

  # some code
end
{% endhighlight %}

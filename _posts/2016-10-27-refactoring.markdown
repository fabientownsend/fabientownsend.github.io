---
layout: post
title:  "Lose Confidence by Refactoring"
date:   2016-10-27 10:42:51 +0100
categories: apprenticeship
---
![ice bar london tiger]({{ site.url }}/assets/tiger.jpg)
Is there a way to refactor and keep the project clean? For me, so far,
I feel that I have to refactor a big mess each time. I'm the only person to blame.

I am currently working on with these three projects:

- Core Tic-Tac-Toe
- Command line Tic-Tac-Toe
- Web Tic-Tac-Toe

The core project is used by both the command line project and the web project
as both need its computer and board implementation.

# Something Seems Wrong

During my implementation of the web version, I noticed some code duplication in
both the command line project and web project. These duplications related to the
management of a party. Here are a few functions that I could find in both project

- game_over
- switch_player
- play_move
- valid_move?
- get_move

I needed to avoid these duplications as they made the project more complicated
to maintain - [I was feeding the monster]({{ site.url }}/pprenticeship/2016/10/10/monster.html)!
At this moment, the best solution was to move the class GamePlay from my
command line to the core project. My web project could delete its duplicated
code this way and use the code from the core project.

It was already too late when I realised that my GamePlay class didn't respect
the single responsibility principle. This made my best solution become the worst.
This class had two responsibilities.

Let's take a look at the code below:

{% highlight ruby %}
class GamePlay
  def menu_board_size
    ...
  end

  def menu_language
    ...
  end

  def menu_game_selection
    ...
  end

  def menu_select_first_player
    ...
  end

  def play
    ...
  end

  def display_board
    ...
  end

  def display_result
    ...
  end
end
{% endhighlight %}

As we can see, this class has the responsibility of the menu, creation of the
game and managing the party. This made impossible to just move this class
to the core project and use it as I did with the board and the computer.

# To Get a Plan

1 - Move the duplication from the web version to the core project.
2 - Make the command line version use the new class from the core project.
3 - Delete the duplication in the command line version.

Here bellow my game closs from the we version:
{% highlight ruby %}
class Game
  attr_reader :current_player
  attr_reader :winner

  def initialize(board, player_one, player_two)
    ...
  end

  def play
    ...
  end

  def over?
   ...
  end

  def winner
    ...
  end
end
{% endhighlight %}

During the refactoring I also moved some responsibilities out of the core project.
For example, it doesn't verify if a move is valid but instead, the board
throw an exception with an error message. Setting a correct move is now the
responsibility of the command line project and web project.

The relationship between the core project and the other projects is now stronger.
All bad decisions become costly when refactoring. This situation makes me feel
less productive as I feel like I have more questions than answers.

The best refactoring is when you don't need to do it. For that, you have to be
right the first time. I should try that.

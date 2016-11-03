---
layout: post
title:  "Losing Confidence by Refactoring"
date:   2016-11-03 10:42:51 +0100
categories: apprenticeship
---
![ice bar london tiger]({{ site.url }}/assets/tiger.jpg)
Is there a way to refactor and keep the project clean? For me,
I feel that I have to refactor a big mess and the intermediated steps make the
code more complicated.

I am currently working on these three projects:

- Core Tic-Tac-Toe
- Command line Tic-Tac-Toe
- Web Tic-Tac-Toe

The core project is used by both the command line project and the web project
as both need its computer and board implementation.

![uml before]({{ site.url }}/assets/refactor_before.png)

We may notice some duplication between the command line project and the web project.
These duplications relate to the management of a party with
the GamePlay class. Here are a few functions that can be found in both versions:

- game_over
- switch_player
- play_move
- valid_move?
- get_move

I needed to avoid these duplications as they make the project more complicated
to maintain - [I was feeding the monster]({{ site.url }}/pprenticeship/2016/10/10/monster.html)!
At this point, my solution was to move the class GamePlay from my
command line to the core project. My web project could therefore delete the duplicated
code and then use the code from the core project.

During the extraction of the class from the cli project into the core project, 
I realised that my GamePlay class didn't respect the 
*single responsibility principle*. This made my solution not as good as I had expected.

Let's take a look at the code:

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

As we can see, this class has three responsibilities: the menu, the creation of
the game and managing the party. This made it impossible to just move this class
from the cli project into the core project and to use it as I did with the board
and the computer.

# Here Are the Steps I Followed to Extract the Class

1. Move the duplication from the web version to the core project.
2. Make the command line version use the new class from the core project.
3. Delete the duplication in the command line version.
4. Delete the class GamePlay in the web version.

See below for the result. My new game class with a simple interface:
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

As a result, we now have this:
![uml after]({{ site.url }}/assets/refactor_after.png)

During the refactoring, I also removed some responsibilities from the
GamePlay class and so, this assured me that this class now respected the *single responsibility principle*.
The GamePlay class no longer verifies if a move is valid. Instead,
I created exceptions that the Board class will throw when a move isn't valid.
The verification of the correctness of a move is now the responsibility of
any project using the Core project.

The relationship between the core project and the other projects is now stronger.
But now, if I have to update my Board or my Computer then I will only have to
change my Core probject. This makes me feel less productive as I feel like I 
have more questions than answers.

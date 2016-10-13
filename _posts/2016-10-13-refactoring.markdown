---
layout: post
title:  "Refactoring the Board"
date:   2016-10-13 10:42:51 +0100
categories: apprenticeship
---

![image git merge]({{ site.url }}/assets/refactor.jpg)
During the previous week, one of my tasks was to add a 4x4 board.Now, here is
how I did it...

I had to modifiy 7 different files in order to achieve this task.
This new feature lets the user choose the size of the board and then allows them
to play a game using it.

Here is the list of the 7 files that I edited:

- interface
- language files
- board_spec
- binary file
- board
- game_play
- game_play_spec

Before talking about the modifications, let's quickly remind ourselves about the
[Open Closed Principle](https://en.wikipedia.org/wiki/Open/closed_principle).
It says:

> In object-oriented programming, the open/closed principle states "software
> entities (classes, modules, functions, etc.) should be open for extension,
> but closed for modification"; that is, such an entity can allow its behaviour
> to be extended without modifying its source code.

In order to see where I broke the Open Closed Principle, let's split my
modifications into two category:

- Extension
- Modification

## Extension

I extended my CliInterface with the *langs* file as well as creating a new menu
for the user.

I managed to set a default value for the board when no size is selected.
By doing this, I will avoid breaking any of my previous tests where the board
size was not set. This will also let me extend the board_spec with new tests.

Out of 7 files, only were 3 got extended.

## Modification

I modified the board's diagonal checker and its data-structure, which was hard
coded with a 3x3 board. Why didn't I do this before? I didn't know how to do
it with Ruby and the spec had been met.

My binary file, GamePlay class and the board had a strong coupling. So,
when I modified the board, I also had to modify the binary file and the GamePlay
class and its tests.

## Conclusion

I feel that I didn't respect the Open Closed Principle. I feel it's hard to predict
the need of future modifications. Could all of the changes be avoided? Probably not.
Could some of them be avoided? Probably yes.

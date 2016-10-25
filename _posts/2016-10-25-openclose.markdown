---
layout: post
title:  "The Open Close Principle"
date:   2016-10-25 10:42:51 +0100
categories: apprenticeship
---
![door train london]({{ site.url }}/assets/openclose.jpg)
The Open Close Principle, also known as OCP, is the second
of the SOLID principles. The Open Close Principle dictates:

> The source code of a system is open for extension, but close to modification.

An application which doesn't respect the OCP is rigid and fragile.
See below description of these symptoms.

- Rigidity: You will have to modify different parts of your system.
- Fragility: When you make a change, you do so with a risk of missing and/or breaking a modification.

For example, you have to modify existing code instead of adding new code when you implement a new feature.
This is an example of what could happen when you don't respect the OCP.

Another example is that you shouldn't test the business rules via the interface.

The abstraction is the key of the OCP.
For that, you need to separate the extensible behaviour through an abstract interface,
which will be used by the application.

Here are some examples of modules that can be extended in my Tic-Tac-Toe project
which shouldn't require modification of the existing code. I should be able to add a new:

-  type of board
-  type of player
-  language

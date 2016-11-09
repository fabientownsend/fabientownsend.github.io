---
layout: post
title:  "Composed Class"
date:   2016-11-07 10:42:51 +0100
categories: apprenticeship
---
![photo pen]({{ site.url }}/assets/pen.jpg)
Working on the controllers of my project, I was wondering what is the relationship
between my controllers and and its composant. I know that it's call *composition*
but, what does it really mean? What does it involve? Here what I understood
after some research.

![notebook uml composition]({{ site.url }}/assets/composition.jpg)

*Composition* describe the relation between classes. This relationship is
considerate as a class A *has-a* class B. Here is some concret example with my
controllers:

- GameCreationController *has-a* Game
- GamePlayController *has-a* Game
- GameCreationController *has-a* Board
- GamePlayController *has-a* Board
- GameCreationController *has-a* PlayersFactory

Game, Board and PlayersFactory are considered as *role* for the composed classes.
The composed classes are made up withs those roles with which they interact via
their interface.

In this realtionship, the contained object has no life out of its
container. Wait what? In my case Game and Board have a life out of their
container. Does it mean it's finally is not a composition?

![notebook uml aggregation]({{ site.url }}/assets/aggregation.jpg)

No, it's just mean that it's a specific *composition*, it's called *aggregation*.
Both are really similar, the particularity of the *aggregation* is that the
contained object have an existence and life out of their container.

---
layout: post
title:  "Coding By Intention"
date:   2016-12-06 10:42:51 +0100
categories: apprenticeship
---
![cover Essential Skills for the Agile Developper]({{ site.url }}/assets/agilecover.jpg)
Have you ever heard about: *coding by intention*? I read about it in the first
chapter of the book *Essential Skills for the Agile Developper*. Let's see
how this concept can help me to find better name for my variables, methods
and classes.

The concept sounds promising, let's check out the advantages listed.
You code will be:

- More cohesive
- More readable and expressive
- Easier to debug
- Easier to refactor/enhance
- Easier to unit test
- Certain patterns will be easier to *see* in your code
- You will tend to create moethods that are easier to move from one class to another
- Your code will be easier to maintain

So how do we archieve that? The first step says that you should write your
method without the implementation, in other words you focus on *what* but no in
*how*. This way, you will focus on your intention without thinking about the contraint.

The second step, determine what your method will need and what does it return.
This is not an obligation, but it seems more natural to pass parameters and then
return the result rather than a nilatic method which modify a global variable.

Third step, the implementation.

I love the idea, I guess I have to try it out now and see if it helps me to improve
my code.

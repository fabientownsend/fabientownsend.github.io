---
layout: post
title:  "Which Principles Did I Broke?"
date:   2016-09-27 10:42:51 +0100
categories: apprenticeship
---

![cover of the book Agile Sofware Development]({{ site.url }}/assets/cover_agile.jpg)
One of my current tasks is to read *Agile Software Development
Principles, Patterns, and Practices* also called *PPP*. I started to read it
today and *PPP* has already had an impact on me. Crazy, right?

This book covers a bunch of interesting subjects for developers, but at the moment,
I am focused on five chapters about the SOLID principles.
The purpose of these principles are to build the best design for current
and future implementations.

As I was struggling to refactor my project, I decided to stop and read this book.

So far I have read two principles:

- Single Responsibility Principle (SRP)
- Open-Closed Principle (OCP)

As I was reading, I realised that the class I tried to refactor earlier
broke the SRP. I felt that my class wasn't correct in the morning, but I
couldn't tell why. This book helped me to identify the reasons why my class
wasn't correct and with this, I could fix the problem.

I managed to extract the methods that broke the SRP into a new class that I
created. Both classes now have one and only one responsibility.

Here is the refactoring pull request: [Github link](https://github.com/fabientownsend/tic-tac-toe/pull/4)
I'm satisfied with the result. I asked for a code review and I can't wait to receive
feedback. I feel that this feedback will help me to assess whether I understood
the information or missunderstood it.

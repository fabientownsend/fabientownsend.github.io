---
layout: post
title:  "What I Learnt From My First Project As An Apprentice"
date:   2016-11-09 10:42:51 +0100
categories: apprenticeship
---
![photo pen]({{ site.url }}/assets/pen.jpg)
One of the things that I love most about 8th Light is the businesses' culture
of learning and sharing our knowledge. I recently finished my Ruby Tic-Tac-Toe
projects, which made me focus on improving my knowledge on the SOLID principles,
 package principle, oriented-object programming and testing software.

Here are 3 important things that I learnt during the different projects, which
improved my software skills:

1. **Later Is a Shortcut For Never** Everything should be done as you go. I
caught myself delaying some little tasks like fault managing, writing tests, etc.
I built an iceberg of tasks that could have become even more difficult to complete
because they didn't belong to other stories.

> Cost-Benefit: An activity will be pursued only if its benefits are equal to
or greater than the costs.

2. **Build Your Own Toy** I used to be a user of web framework that had no
idea about how it worked. I struggled to fix it each time that it broke . I
have since realised how *fast* and *easy* it is to understand how it works:
build a simple version of these tools. Trust me, you will feel really better
when you realise software is only just about input and output, nothing more.

3. **Dependencies are Hard to Maintain** Whenever you change a variable, a method,
a class or an extension name, this change will imply a modification of everything
depending on it. When it's in the same project, editing the name is pretty
easy with an IDE. The project can quickly become a nightmare to maintain when
you depend on external repositories or externl dependencies.

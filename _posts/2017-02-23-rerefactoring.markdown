---
layout: post
title:  "When to Stop Refactoring"
date:   2017-02-23 10:42:51 +0100
categories: apprenticeship
---
![note book]({{ site.url }}/assets/notebook.jpg)
Have you ever felt the urge  to refactor a chunk of code that you came across?
Thought, this code looks awful, I better do a quick refactoring?

Refactoring has an important problem. Refactoring is an infinite process, the
same problem can have many solutions. This makes it complicated to know when it
is finished, and refactoring isn't a task by itself, we aren't paid to deliver
a refactoring.

Let's dig a bit on what can cause the need for refactoring.

“Shipping first-time code is like going into debt. A little debt speeds
development so long as it is paid back promptly with a rewrite… The danger
occurs when the debt is not repaid. Every minute spent on not-quite-right code
counts as interest on that debt. Entire engineering organizations can be brought
to a stand-still under the debt load of an unconsolidated implementation,
object-oriented or otherwise.” - Ward Cunningham

According to Ward Cunningham, we can assume that technical debts are created on
purpose, but we have to repay our technical debt and refactoring help that. If
we aren't paid for refactoring but have to refactor in order to repay our
technical debt, what can we do?

Write good code. This sounds obvious, but good code makes the code easier to
refactor. Whenever you know that you create a technical debt, keep in mind that
you or someone else will have to repay the debt.

Focus on your task. When you work on a chunk of code, it's the perfect time to
refactor it, but only if this code belongs to your task. Otherwise, you can
still create a ticket/task for it.

Know when to stop. Is the code well tested? Have you repaid the technical debt?
Is the code better than when you started? It's may be the right time to stop
here and avoid to turning around in a circle of refactoring.

Practice, just like TDD, debugging or whatsoever, refactoring is a proper
discipline, and the only way to improve is to practice. The book "work
effectively with legacy code" can be a good start to training this skill.

Keep in mind that the code is never finite but rather something that changes
and evolves overtime. Whenever you come across code that seems horrible to you,
don't let it drive you to frenzied refactoring, instead let your drive be what
could have a positive impact on the software, your customer, and users.

---
layout: post
title:  "Are Your Tests Maintainable?"
date:   2016-10-06 10:42:51 +0100
categories: apprenticeship
---

![google survey about tests]({{ site.url }}/assets/survey.jpg)
Tests are good, maitainable tests are better.

Our code is thoroughly tested here at 8th Light. One of our values is to not
tolerate preventable defects. Our code is systematically tested through unit
and integration tests.

In my current project Ruby Tic-Tac-Toe, I have an average of 1,5 tests for each
public method.

- Gameplay: 13 tests 4 public method
- Board: 12 tests 5 public method
- Computer: 6 tests 1 public method
- Human: 2 tests 1 public method
- Factory: 5 test 3 public method
- Interface: 11 tests, 16 public methods

As we can see, there are more tests than public methods in total.
When tests are put in place to improve the design, document and
to maintain the project, what maintains the tests?

Previously, I had a hard time refactoring my project's code
because I had a habit of testing my methods, including the private ones.

I ask for my colleagues opinion of how to improve tests so I could learn and
improve.
Here is the feedback:

- Try to only depend on the public interface.
- Refactor it continually.
- Keep it isolated.
- Ensure it has one responsability.
- Write the minimum needed.
- Keep it short, clear and concise.

Notice that all of this advice could also applied to production methods.
Tests are also methods, aren't they?

Tests shouldn't be treated differently to the rest of the code. They both
need to be high quality in order to improve the maintainability of the project.

So, I think I have some refactoring to do with my tests!

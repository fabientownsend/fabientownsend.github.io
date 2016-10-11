---
layout: post
title:  "My Ressources For My First Package"
date:   2016-10-11 10:42:51 +0100
categories: apprenticeship
---

![notes for my packaging]({{ site.url }}/assets/notes.jpg)
I will soon start coding the web version of my Tic-Tac-Toe. Before this, I need to
isolate and package the code that will be used in both version of the application.

I will identify different actions that will allow me to achieve my goal.
Firstly, I'll identify which parts need to be encapsulated, then create the Gem
and finally install this Gem in the different versions of the project.

As I don't have any experience with packages yet, I will not go in further
detail in this article. I will share the first resources that I found to help
me with this task.

# Principles
SOLID component with Uncle Bob: [SOLID components](https://cleancoders.com/videos#clean-code-episode-15)

The book **Agile Software Development, Principles, Patterns, and Practices**
with a focus on the following chapter:

IV. PACKAGING THE PAYROLL SYSTEM.

- 20. Principles of Package Design.
- 21. Factory.
- 22. The Payroll Case Study (Part 2).

Principle of Package Cohesion:

- Reuse-release equivalence principle (REP)
- Common-reuse principle (CRP)
- Common-closure principle (CCP)

Principles of package coupling:

- Acyclic dependencies principle
- Stable-dependencies principles (SDP)
- Stable-abstraction principles (SAP)

Source: [wikipedia package principles](https://en.wikipedia.org/wiki/Package_principles)

# What About Ruby?
I have listed below the tools in Ruby that I will need to learn in order to
achieve my task.

To create a package:
[rubygems](https://rubygems.org/)

Install a package:
rubygems

Isolate runtime version:
[rvm](https://rvm.io)

Sandbox your packages:
rvm + [bundler](http://bundler.io/)

Specified dependencies:
bundler with Gemfile

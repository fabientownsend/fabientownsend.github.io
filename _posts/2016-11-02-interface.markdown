---
layout: post
title:  "What Instead of Telling How"
date:   2016-11-02 10:42:51 +0100
categories: apprenticeship
---
![practical object-oriented design in ruby cover]({{ site.url }}/assets/oop.jpg)
In programming, *things* communiques with each other through public interfaces,
no matter if those *things* are classes, a web services or a package. These
public interfaces must be flexible as possible in order to keep them usable
by their users.

Interfaces can be private or public:

**Private Interface**
The private interface contain the details and its mechanism. It is not supposed
to be used by anything else but the class itself. This let us make any change
without breaking any user of this class. The private interface isn't necessarily
tested.

**Public Interface**
The public interface is here to provid public methods with explicite name. Its
name neither its signature should change, otherwise everything which depend on
it will have to be update, included its unit tests and frankly, you don't want
that. Everything about this interface should be document with unit test,
those will explain how to use the interface and what to expect about it.

If you ever have to modify this interface it can be a good idea to create a v2.

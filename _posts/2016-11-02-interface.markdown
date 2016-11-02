---
layout: post
title:  "What Instead of Telling How"
date:   2016-11-02 10:42:51 +0100
categories: apprenticeship
---
![practical object-oriented design in ruby cover]({{ site.url }}/assets/oop.jpg)
In programming, *things* communiques with each other through public interfaces,
no matter if those *things* are classes, a web services or a Gems. As they
depend to these public interfaces, these interface must be flexible as possible
and avoid any modification that could break the user of this interface.

Interfaces can be private or public:

**Private Interface**
The private interface contain the details and the mechanism. It is not supposed
to be used by anything else but the class itself, letting us make any change for
any reason without have to worry to break anything depending on it.

**Public Interface**
The public interface is here to provid public methods with explicite name which
must never change neither their signature of their return. Everything about this
interface should be document with its Unit Test. It explain how to use
the interface and what to expect about it.

Of course, any modification of this public interface will affect thos who depend
on it. This will garantis you a hard time to repear everything, include its tests.
If you ever have to modify this interface it can be a good idea to create a v2.

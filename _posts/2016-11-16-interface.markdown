---
layout: post
title:  "Interface"
date:   2016-11-16 10:42:51 +0100
categories: apprenticeship
---
![kindle charching]({{ site.url }}/assets/kindle.jpg)
One noticable difference between Ruby and Java is the presence of interfaces.
In Java, interfaces are composed by a set of public signatures which doesn't
include implementation neither data properties.

That's a really good advantage, it allow us to keep seperated the interfaces to
the implementation. To exploid this sepration, the *clinet* will communicate
to the class throught their interface regardless which class implement this
interface.

This flexibility is really great, it will let us change the class that
implement the interface whenever it needed and for our test we will
be able to inject a fake that respec this interface!

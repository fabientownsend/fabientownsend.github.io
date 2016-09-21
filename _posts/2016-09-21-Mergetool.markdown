---
layout: post
title:  "Trade Offs"
date:   2016-09-21 10:42:51 +0100
categories: apprenticeship
---

![cup of coffee]({{ site.url }}/assets/conflict.jpg)
One of the most useful features of Git is its *branch* system. This system allows you to create independent branches
for each of your features, and then merge them together.

With great features comes great responsability: the merge confict.
Merge conficts can happen when two of the same edited files attempt to merge together. This is where Git is fantastic
as it can resolve merge conflicts by itself, most of the time...

Today I had to merge two branches to my trunk (the main branch of a project). That was a disaster; thankfully, I created
a third branch dedicated to this merge. I followed this work flow:

- Create a new branch based on trunk
- Merge my features to my new branch
- Delete this branch when I feel it has become too messy and I want to do it again from scratch

I know that this isn't the academic way, but it was efficient as I could resolve it after 4 atempts (oops).

I also updated the configuration of my Git. From now on, Git will use vimdiff to help me to sort out this big mess.

Here is the short version:

{% highlight shell %}
git config merge.tool vimdiff
git config merge.conflictstyle diff3
git config mergetool.prompt false
{% endhighlight %}

Then:

{% highlight shell %}
git mergetool
{% endhighlight %}

Here is the long version: [tutorial](http://www.rosipov.com/blog/use-vimdiff-as-git-mergetool/)

I wasn't confident with resolving this conflict and my new settings didn't really help me either.
I finally merged everything and didn't break my trunk so I think it wasn't that bad.

I still have my book Git Pocket Guide to read. It can only help me to improve, right?

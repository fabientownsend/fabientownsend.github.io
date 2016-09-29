---
layout: post
title:  "Some Git Commands"
date:   2016-09-28 10:42:51 +0100
categories: apprenticeship
---

![cover of the book Agile Sofware Development]({{ site.url }}/assets/cover_agile.jpg)
Git is an amazing versioning tool with a tonne of commands.
Here are the 8 last commands that I added to my daily workflow.

This post is more of a memo that I have written in order to remind myself of
the few commands that I learnt.

To add a specific change from a file, add the keyword *patch* after the *add*

{% highlight shell %}
git add -patch your_file
git add -p your_file
{% endhighlight %}

Display all the branches, not just the local one:

{% highlight shell %}
git branch --all
{% endhighlight %}

Delete a remote branch from origin:

{% highlight shell %}
git branch push origin :branch_to_delete
{% endhighlight %}

Display the difference between your working tree and the index.
This is really practical if you need to see the changes that you have already
committed.

{% highlight shell %}
git diff --cached
{% endhighlight %}

Unstage all of the local commits:

{% highlight shell %}
git reset
{% endhighlight %}

This one is powerful as you can edit your staged commit(s). For the moment, I only use
this command to edit messages that I committed  or their order.
You can do a lot more with this command.

{% highlight shell %}
git rebase -i HEAD~4
{% endhighlight %}

Here is a way to save a file without committing it. This command will let you
checkout out on another branch or whatever you need.

{% highlight shell %}
git stash pop
{% endhighlight %}

Here is the way to get back your stash:
{% highlight shell %}
git stash pop
{% endhighlight %}

Another thing I learnt is that if you have to edit a filename, it is best to
have a dedicated commit for this change. It will be easier to spot the change
in the logs and will therefore help to  avoid any confusion.

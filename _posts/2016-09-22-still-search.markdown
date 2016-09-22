---
layout: post
title:  "Mapping With Vim"
date:   2016-09-22 10:42:51 +0100
categories: apprenticeship
---

![cup of coffee]({{ site.url }}/assets/conflict.jpg)
As a developer, you have the skills to automate tasks. Something that I
don't do enough.

Since I started to learn Ruby 3 weeks ago, I have been testing
my software in this way:

- leave Vim to my terminal with *ctrl+Z*
- launch my test with *rspec*
- return to Vim with *fg*

That way is actually quite long and, quite frankly, boring. There are better ways to
do it, but which one should I choose? I didn't know.

I could install a Gem that will look at my files and launch the tests each
time that the files are saved. I wasn't convinced enough to install this nor to
configurate an external tool.

Instead, I found a cool mapping for Vim. I saw this in a video from
[destroyallsoftware.com](www.destroyallsoftware.com)

It's simple, isn't it? {% highlight shell %}
:map <cr> :w\|!rspec <cr>
{% endhighlight %}

You can also configurate it for any project or task. That is cool!

Here are the details:

:map    - writes a new mapping for your current session of Vim
<cr>    - corresponds to the enter key
:w      - saves the current file
\|      - "\" escape the character "|" which is a pipe, this will make the next command launch after saving
!respec - launchs my Ruby tests, but could be adapted to any other language

Now I only need to type enter once and it will launch and display my tests. 
When I push enter a second time, it returns to my code!

---
layout: post
title:  "Git log"
date:   2017-01-24 10:42:51 +0100
categories: apprenticeship
---
![note book]({{ site.url }}/assets/notebook.jpg)
Are you like me, struggling to keep your git log clean? Here is
the way I'm working on improving it.

The basic, is how to name you commit. For that I'm apply what I read
in this excelent article [chris beams: git commit](http://chris.beams.io/posts/git-commit/).
Basically each commit start with a verb and what will be applied with this commit,
for example:

- Add a new feature for user order
- Update dependency of tests
- Fix typo in readme api explanation

This is really important, because everytimes you will have to:

```
git reflog

git reset --hard HEAD@{1}
```

Don't gringe about the reset --hard, things happend!

That's why you should always, always working on a branch and then
merge it with merge --no-ff or a rebase depending if you need
to make it appear in your log.

Talking about branch, here are two command I use since some days:

- git checkout heroku/branch -b new_branch
- git push heroku localbranch:remotebranch

The second command was useful for testing a branch on the heroku master.

The last be no least, git rebase -i. I use this one all the time.
It let me edit my commits, change their order, squash and split previous
in smaller commint.

Here how you can split a previous commit, by editing the commit that you want.
```
git rebase -i HEAD~5
git reset HEAD~
```

With those command there is really matter to mess up with you repository, but
it definitly worth to learn it if you consider your git logs/versioning as
important as your code.

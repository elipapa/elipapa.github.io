---
layout: post
title: "I keep configuration files in a repo"
date: 2013-03-23 16:27
comments: true
categories: 
published: false
---

TODO add links

Most people either place all their [dot files in Dropbox]() or a [repo]() to sync them across machines. What I don't like about the first option is that if you want to just sync your dot files on a headless machine (often done for computing clusters) you first need to [install dropbox from the command line]() and then sync the content of the entire dropbox directory. I don't know about yours, but my dropbox is too large and has far too many personal things for this to be feasible (and accepted by my sys-admin). 

I have used the second option for a while, [storing my dot files on bitbucket](), but this isn't perfect either. Every time you want to sync changes you need to make at least a push on one side and a pull on the other. This can easily break the flow of whatever you were working on (usually that work which a fix of the config files was trying to facilitate in the first place).

To solve this problem I have tried using [Fabric](), a python tool which is made for remote deployments of apps. A little time working on the *fabfile* and then I only have to type

    fab update

from the machine I am working with to keep all my hosts in sync. I can list which hosts should be updated and include my central repo in there to make sure a master copy exists somewhere else than my laptop. 

It is quite a flexible system, because it allows me to keep system-specific patches. 

[Dotsync](https://github.com/dotphiles/dotsync) does something quite similar, but it looks a tad too complicated to set up at first sight. Since this is the kind of thing that happens regularly, but not often enough to remain in my working memory, the more complex and featureful the system is, the higher is the probability I will forget how it works. 

[Movein](http://stew.vireo.org/movein/README/) is another tool that does the same thing and I like that it tries to keep everything modular. It does so by keeping separate repos and relying on [mr](http://joeyh.name/code/mr/) to manipulate them in parallel. It then synchronizes only the ones needed on each system. For eg. `mr add shell` and not `mr add emacs` if all you need is bash aliases and not all your crazy emacs configurations. [Caretaker](http://derf.homelinux.org/projects/caretaker/) does the same thing. The issue with both is that a fair amount of git initial setup has to be done: that's fine if you never forget your git commands, but if you have my poor memory this approach is simply too complex. I need something that keeps it simple, even if at the expense of features.
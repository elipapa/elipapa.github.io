---
layout: post
title: "How i fixed my corrupted sparsebundle image"
date: 2015-11-02 13:01
tag: 
- tech
- geeky
- stackoverflow
projects: false
category: blog
author: elipapa
---


I save all my paper scans and important documents in an encrypted sparsebundle. In lieu of proper backup, I place the file in my dropbox. However, when I got too defiant and tried to use the same image from more than one computers connected to dropbox, the image was corrupted and could not be mounted anymore. Panic.

How do i repair the sparsebundle image i had in dropbox?

Apparently this happened more than once. A quick google search returns a bunch of questions on stack overflow trying to find a way around it. Not many with encouraging results. Sparsebundles are treated as directories by dropbox and it's not possible to restore entire directories at once from the graphical interface. But encrypted bundles are definitely not directories and as soon as two computers change a chunk at the same time, mayhem occurs.

After a while, however, I did come up with something: There is a python command called [dropbox-restore](https://github.com/clark800/dropbox-restore) which interfaces with the dropbox API and retrieves every independent file in the directory (or sparsebundle) at a certain time stamp.

I haven't tested it, but I ended up installing installing an alternative called [revisions app](https://www.revisionsapp.com), which gives a graphical interface to the same functionality and a lot more ways of interacting with the dropbox API. It was free to install and after 2-3 hours of indexing work, i was able to succesfully retrieve my encrypted sparsebundle down to a date when it was not corrupted.

This near disaster taught me the importance of [splitting syncing and backup](http://lifehacker.com/psa-dropbox-shouldnt-be-your-sole-backup-for-your-file-1612803794).

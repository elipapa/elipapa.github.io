---
layout: post
title: "What is the fastest way to find duplicate pictures?"
date: 2015-02-19
comments: true
category: blog
---
I needed to clean up duplicates photos from my personal library. And because I could not choose which duplicate finder to try, I have decided to test them all. Amongst the free tools that were correct in identifying all duplicates in my test, [dupd](https://github.com/jvirkki/dupd) was the fastest. Other [python](https://www.python.org/) and [perl](http://www.perl.org/) based solution did also very well, often better than their C/C++ colleagues.

## Why a duplicate file finder? 
As a parent, my picture collection has mushroomed in size. I do try to save everything in one place and have backups, but it is difficult to keep track of it. Too afraid of losing family memories, often I end up downloading pictures from my phone multiple times, "just in case". Now that I have reached the limits of my hard drive space, I figured the best thing to do was to remove some duplicate pictures.

One could try with iPhoto or some other graphical interface, but the approach is simply too slow for a large library (over 100GB). The obvious choice was to search for a command line tool.

I quickly realized that **there are far too many tools** which have been written for this task. And no easy way to find which one is best. So I decided to compare the speed of most of them.

## A speed comparison
Wikipedia has a pretty complete [list of duplicate file finders](http://en.wikipedia.org/wiki/List_of_duplicate_file_finders). From there I downloaded and installed all free/open source command line tools.

I have excluded from this comparison those tools which could not be readily installed on my macbook (eg. Makefile would have needed fixing) or appear to have very limited support (less than 10 stars on github, slow or stagnant development, etc.).
I did not take into considerations those tools that do not have the option of a "dry run" or simple listing of duplicates, but instead attempt to delete or hardlink the duplicate files. I find this behaviour too aggressive for most users. Definitely too risky to run on the folder containing the pictures of my kids.

Finally, I excluded those files that failed to find all correct duplicates in my test folder. The folder was designed to contain 1195 duplicates in 325 clusters. Here are the results, tested on a 7GB mixture of pictures, videos, symlinks, small files and recursively nested files:  

<iframe width="700" height="450" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/1zEaULNBhh-ynwpDnLDZT56rAOeupGKgoSblyREEfSbw/pubchart?oid=377382474&amp;format=interactive"></iframe>

Since I keep my pictures in a separate NAS storage, it is also useful how much each of this methods hinges on memory or CPU:

<iframe width="700" height="450" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/1zEaULNBhh-ynwpDnLDZT56rAOeupGKgoSblyREEfSbw/pubchart?oid=980882643&amp;format=interactive"></iframe>

<iframe width="700" height="450" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/1zEaULNBhh-ynwpDnLDZT56rAOeupGKgoSblyREEfSbw/pubchart?oid=903055661&amp;format=interactive"></iframe>


## Conclusion

[Dupd](https://github.com/jvirkki/dupd) was the clear speed winner, also with an acceptable memory footprint. [liten](http://code.google.com/p/liten/) and [fastdupes](http://ssokolow.com/scripts/#fastdupes.py) come close second and may be slightly more portable as they do not require to be compiled. Compiling of the C/C++ tools tend to be a little fragile out of the main UNIX distros, which is a problem when working on a NAS. **I ended up using [fastdupes](http://ssokolow.com/scripts/#fastdupes.py)**.

It is interesting to see how the (arguably) best known solution [fdupes](https://code.google.com/p/fdupes/) was also the slowest. Though it remains one of the only tools which can do byte-by-byte comparison. Both the fastest and second fastest tool rely on [SQLite databases](http://www.sqlite.org/) and allow you to explore duplicates interactively, after they run. 

Please let me know if I forgot any other tool which should have been in this list. The commands included in the analysis were:

 * [duff](http://duff.dreda.org/) (C)
 * [dupseek](http://www.beautylabs.net/software/dupseek.html) (Perl)
 * [fastdupes.py](http://ssokolow.com/scripts/#fastdupes.py) (Python)
 * [fdf](http://www.iredale.net/p/by-permalink/449447C8-EACB-11DC-B77B-21EB6225452B/) (perl)
 * [fdupe](http://freshmeat.net/projects/fdupe/) (perl)
 * [fdupes](https://github.com/adrianlopezroche/fdupes)(C)
 * [fdupes-jody](https://github.com/jbruchon/fdupes-jody) a speedier fork of fdupes (C)
 * [liten](http://code.google.com/p/liten/) (Python)
 * [liten2](http://code.google.com/p/liten2/) (Python)
 * [rdfind](http://rdfind.pauldreik.se/) (C)
 * [ssdeep](http://ssdeep.sourceforge.net/) (C) also does partial matches
 * [python active state recipe](http://code.activestate.com/recipes/551777/) (Python)
 

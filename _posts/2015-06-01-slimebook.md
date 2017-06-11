---
layout: post
title: "SLiMEbook"
date: 2015-06-01 10:00
tag: 
- project
- ipython
- ML
projects: false
category: blog
author: elipapa
---

I published an IBD paper [in PLoSONE](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0039242) - showing one of the first application of ML methods to microbiome data. We dubbed the code used for the analysis SLiME.

The SLiME code (written in [R][]) became outdated pretty quickly. We decided that the code, as it was packaged for the publication of the paper, should not be in the open anymore. 

In its place, [this ipython notebook][notebook] will serve as a repository of the analysis. I hope this can be the starting point for others trying to follow the same approach and improve upon it. It leverages python, sklearn and pandas.

Check the full [repo][SLiMEbook], which also contains the [raw data][data]

[notebook]: http://nbviewer.ipython.org/github/elipapa/SLiMEbook/blob/master/SLiMEbook.ipynb 
[SLiMEbook]: https://github.com/elipapa/SLiMEbook/
[R]: https://www.r-project.org/
[data]: https://github.com/elipapa/SLiMEbook/tree/master/data/chimp
---
layout: post
title: "Install Circos on a Mac using homebrew"
date: 2013-05-09 11:26
comments: true
categories: 
published: false
---

There already exist [some instructions]() on how to install [Circos]() and all its dependencies on Mac OS X. However, they can be make much simpler if you rely on [homebrew]() as a package manager on Mac (if you don't you most definitely should).


(If you want to be fancy you can install [perlbrew]() which lets you have different versions of perl than the standard one shipped with Mac OS X)


	brew install gd

One of the test still fails in make test and cpan refuses to comply. To solve that problem, just: 

	cpan> force install GD

A last call of:

	./test.modules

should show all ok's. Now you are ready to go.
---
layout: post
title: "fix ruby and bundler after upgrading openssl"
date: 2014-12-19 13:01
categories: stackoverflow
---

I had trouble running [bundler](http://bundler.io) on this blog because of a ruby error. Though I am not sure what I have broken for this to occur, it appears that ruby could not find openssl libraries anymore. A quick search on [stack overflow](http://stackoverflow.com/questions/25492787/ruby-bundle-symbol-not-found-sslv2-client-method-loaderror) pointed me on the [right direction](https://github.com/sstephenson/rbenv/issues/610). Apparently upgrading openssl via homebrew breaks ruby dependencies. What I had to do was to install another ruby version with my ruby manager of choice ([rbenv](https://github.com/sstephenson/rbenv)):

    CFLAGS='-g -O2' RUBY_CONFIGURE_OPTS=--with-openssl-dir=`brew --prefix openssl` rbenv install 2.2.0
    rbenv global 2.2.02
    rbenv rehash
    gem install bundler

And that was enough to bring me back to square one.

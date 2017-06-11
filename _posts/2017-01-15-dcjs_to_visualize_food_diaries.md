---
layout: post
title: "You Are What You Eat - an interactive visualization of food data"
date: 2015-06-02 15:45
comments: true
tag: 
- project
- D3
- data science
projects: false
category: blog
author: elipapa
---

I have created a [visual dashboard](http://elipapa.github.io/youarewhatyoueat/), which allows to explore daily food diaries. I wanted to try using some of the interactive capabilities of [D3.js](https://d3js.org/) and [Crossfilter](http://square.github.io/crossfilter/). I have ended up leveraging the [dc.js](https://dc-js.github.io/dc.js/) library, which integrates the two with good templates.

The data is scraped from 200 users of the MyFitnessPal app, who shared their food logs publicly. I used [um.ai](http://um.ai) ontology of food to categorize each food item in its food group and to estimate the calories and macronutrients consumed.

While quite easy to use and visually appealing, using dc.js still required  a bit of attention. Sure, my javascript skills are minimal, but there were a number of little details which required to dig into stackoverflow,etc.
It's a good tool to create and expose stable dashboards, but probably not great for quick prototyping of different metrics.

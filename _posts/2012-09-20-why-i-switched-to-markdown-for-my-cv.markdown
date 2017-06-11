---
layout: post
title: "Why I switched to markdown for my CV"
date: 2012-09-20 15:46
comments: true
tag: 
- project
- css
- jekyll
projects: false
category: blog
author: elipapa
---

I have previously used [LaTeX](http://www.latex-project.org/) to typeset my _curriculum vitae_, as it invariably produces a beautiful looking document. I have now become frustrated at how long it takes me to relearn LaTeX from scratch every time I want to change something. Plus my `.tex` source file was becoming completely unreadable. In an attempt to clear up the mess, I decided to put all the content in a markdown file and use CSS to style it. The result is [markdown-cv]({{ site.url }}/markdown-cv/), which can be forked and used as a template by anyone who wants to do the same thing.

I have kept my _curriculum vitae_ in [LaTeX](http://www.latex-project.org/) for a long time. My workflow included a plain text [editor](http://www.gnu.org/software/emacs/) and a [Mac installation of LaTeX](http://www.tug.org/mactex/). LaTeX's elegant typography meant my CV would always look a tad better than its corresponding version in word, and I stuck to it. I also enjoyed having to deal only with plain text files, saving me from the converting files from one word processor to the other. Not to mention that having a single file to update, rather than a series of word processor files scattered everywhere, kept me more disciplined about updating it regularly.

However it was definitely not perfect. For a document as short as my CV, LaTeX was probably overkill. One or two hours spent in word can easily produce a new style or version of the CV, while doing the same thing in LaTeX would always require much more tinkering.
I began to get tired of sparkling small LaTeX commands throughout the file, adding `\vskip` and page breaks to maintain the overall appearance. Albeit plain text, *the LaTeX file which contained my CV became increasingly less readable.* Though the primary purpose of LaTeX should be to separate content from presentation, the division was becoming to me always less evident. The last drop was when I tried to update the overall look of my resume. I ended up having to rearrange paragraphs and dates, while making up obscure LaTeX macros just to move the years to a different place or change the color of a particular element.

Having recently worked with static blog engines, I immediately thought the division between content and presentation was much more elegant there. The content is usually kept in [Markdown](http://daringfireball.net/projects/markdown/), which is very easily readable in any text editor and can be readily converted to HTML. Styling the content is done using CSS and can be done differently for print media or for visualization in a web browser using [media queries](http://www.alistapart.com/articles/goingtoprint/).

So I proceded to transfer my CV in Markdown format, created a simple HTML template and rendered it using [jekyll](https://github.com/mojombo/jekyll), the engine used by [GitHub](http://www.github.com) to render static pages (and what I use to render this blog). I created a CSS to render the page in a style inspired by [kjhealy's vita template](http://kjhealy.github.com/kjh-vita/).

To obtain a [pdf][pdffile] version of the cv, I am using the great [wkhtmltopdf](http://code.google.com/p/wkhtmltopdf/), which I call by means of a [rake](http://rake.rubyforge.org/) task: `rake pdf`.

You can see the various pieces of the workflow arranged on [GitHub][gh] (Hosting on GitHub there also means I can maintain different versions of the same file, eg. one resume for tech jobs and another for academic purposes). I am quite happy with the [final result]({{ site.url }}/downloads/cv.pdf).

I can't say that this workflow was completely succesful in doing away with the tinkering, but at the very least the main content of my curriculum vitae is now available in plain readable text. I can easily edit it without having to remember any LaTeX commands. That and I needed the CSS practice...


[pdffile]: {{ site.url }}/downloads/cv.pdf
[gh]: https://github.com/elipapa/markdown-cv

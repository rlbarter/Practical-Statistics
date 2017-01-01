---
layout: post
title:  "How to post your blog post"
author: Rebecca Barter
categories: [introduction]
tags: [publishing, blog posts]
---



So... how does one get their blog post on here? That's an excellent question and I'm so glad that you asked! 

It's quite easy, really (especially if you avoid the advanced steps which will require you to spend some time pulling out your hair trying to understand how jekyll, github pages, and R Markdown interact with one another).

All you need to do is follow the so-simple-and-easy-to-implement steps below! Hooray!




## Step 1: Fork the github repository

First thing's first, you need to **fork the git repo** on which this site is hosted: [https://github.com/rlbarter/Practical-Statistics](https://github.com/rlbarter/Practical-Statistics). Basically you will write the following code in the **command line** i.e. terminal (assuming that you've installed git at some point in your life):



{% highlight bash %}
git fork https://github.com/rlbarter/Practical-Statistics
{% endhighlight %}


## Step 2: Write your blog post using R Markdown

Write your blog post in RStudio as an R Markdown file, and save your `.Rmd` file in the `/_source` folder <font color="red">this lives on the `gh_pages` branch</font>.


## Step 3: Submit a pull request

<font color="red">Note that the website content lives on the `gh-pages` branch... I need someone who is more familliar with forking and making pull requests than I to write about how to do this. All .Rmd posts will be added to the `/_source` folder in the `gh-pages` branch</font>


Do the things

## Advanced steps

If you would like to be able to render the website locally on your machine before submitting your post or any changes to the public version, you need to install [ruby](https://www.ruby-lang.org/en/downloads/) and then [jekyll](https://jekyllrb.com/docs/installation/). 

Having done this (possibly with a huge amount of frustrated hair-pulling), you can simply install the `servr` package in R:


{% highlight r %}
install.packages("servr")
{% endhighlight %}

and then run the `jekyll()` command


{% highlight r %}
servr::jekyll()
{% endhighlight %}

If this doesn't work, it make sure that you have indeed installed ruby and jekyll. Otherwise, your problem will likely be solved by specifying the path to the `jekyll build` command (found using `which jekyll` in the terminal).

For instance, in order to build and serve the website locally, I need to use the following argument:


{% highlight r %}
servr::jekyll(command = "~/.rbenv/shims/jekyll build")
{% endhighlight %}


Note that due to laziness, this site was essentially copied from Yihui Xie's kitr-jekyll repository https://github.com/yihui/knitr-jekyll. Gi


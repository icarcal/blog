---
layout: post
title:  "Blogging with Jekyll! [1/2]"
date:   2015-07-14 01:16:00
categories: jekyll beginner
thumbnail: gravatar
tags:
 - jekyll
author: Icaro
---

### Begin blogging with Jekyll and GitHub

Hi folks!

Thats the story of how I started to blog with Jekyll.

First of all, there's a **lot** of information on the official [Jekyll] website, what, at first, may be a little freacking.

As my first post, I'm going to show what I did to bring this blog up.

You can begin your blog with no teminal skills, every command is here :D

#### Step one: Requirements

There is a few requirements for you to blog with Jekyll:
 
 - [Ruby]  \(including development headers\)

 - [RubyGems]
 
 - Linux, Unix, or Mac OS X
 
 - [NodeJS], or another JavaScript runtime (for [CoffeeScript] support).

#### Step two: Install Jekyll

Run the following command to install Jekill:

{% highlight sh %}
~ $ gem install jekyll
{% endhighlight %}

**Tip: Run it with sudo if you have access problems**

After that, your blog plataform is installed.

#### Step Three: Create your blog

After Jekyll's installation, we need to create our blog.
Create a folder with the name you want to your blog, in my case was icarcal.github.io

{% highlight sh %}
~ $ mkdir your_blog_name
~ $ cd your_blog_name
{% endhighlight %}

After that, run the following code to create your blog

{% highlight sh %}
~ $ jekyll new .
{% endhighlight %}

or, if you want to do it all at once:

{% highlight sh %}
~ $ jekyll new your_blog_name
{% endhighlight %}

**This command will create the folder and initialize a new Jekyll blog**


[Jekyll]: http://jekyllrb.com/
[Ruby]: https://www.ruby-lang.org/en/downloads/
[Rubygems]: https://rubygems.org/pages/download
[NodeJS]: https://nodejs.org/
[CoffeeScript]: http://coffeescript.org/
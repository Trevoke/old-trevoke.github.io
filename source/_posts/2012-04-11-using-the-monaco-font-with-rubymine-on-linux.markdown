---
layout: post
status: publish
published: true
title: Using the Monaco font with Rubymine on Linux
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 327
wordpress_url: http://trevoke.net/blog/?p=327
date: 2012-04-11 12:36:43.000000000 -04:00
categories:
- ruby
- rails
tags:
- linux
- rubymine
- monaco
- font
comments: []
---
Here are the things you need to know about using any new font for Rubymine:
<ol>
	<li>It needs to be <strong>Unicode</strong></li>
	<li>It needs to go into the $JDK_HOME/jre/lib/fonts directory</li>
</ol>
That is absolutely it. The last thing is the Monaco font, which <a href="http://trevoke.net/blog/wp-content/uploads/2012/04/Monaco.ttf_.zip">I have attached</a> for your downloading pleasure. It turns out DejaVu Sans Mono just isn't as nice -- however nice it may be -- and Inconsolata XL doesn't quite do it for me either.

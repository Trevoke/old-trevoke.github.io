---
layout: post
status: publish
published: true
title: irb tab completion in Windows
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 94
wordpress_url: http://trevoke.net/blog/?p=94
date: 2009-03-30 15:20:04.000000000 -04:00
categories:
- ruby
tags:
- ruby
- irb
comments: []
---
This is good for 1.8.6
In your ruby\bin directory, there should be an 'irb.bat' and an 'irb' file. Edit that 'irb' file.
all you have to do is add :
require "irb/completion" 
under 'require "irb" ' and you're set.

If you have 1.8.7, it looks like that's in the irb.bat file instead..

And if you have 1.9, it looks like the tab completion is automatically enabled, lucky us! (unless I made a change and forgot about it).

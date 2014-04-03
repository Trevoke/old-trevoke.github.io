---
layout: post
status: publish
published: true
title: www.learningrails.com tutorial - screencast 14, in_place_editing
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
excerpt: How to fix a problem with screencast 14 and raw HTML displayed.
wordpress_id: 112
wordpress_url: http://trevoke.net/blog/?p=112
date: 2009-04-23 18:46:48.000000000 -04:00
categories:
- ruby
- rails
tags:
- rails
- in_place_editing
comments: []
---
You'll notice, if you follow those screencasts (around now, anyway, as the plugin's code is likely to change, or maybe the screencasts themselves) that when you add in_place_editing, you suddenly get broken HTML..

The fix is thankfully easy!

vendors > plugins > in_place_editing > lib > in_place_macros_helper.rb
Line 79:
tag = content_tag(tag_options.delete(:tag), h(instance_tag.value(instance_tag.object)), tag_options)

Change to :
tag = content_tag(tag_options.delete(:tag), instance_tag.value(instance_tag.object), tag_options)

And you're set!

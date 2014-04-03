---
layout: post
status: publish
published: true
title: Rubygems through a proxy with authentication
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
excerpt: How to use Rubygems when behind a proxy that requires authentication
wordpress_id: 136
wordpress_url: http://trevoke.net/blog/?p=136
date: 2009-09-09 08:58:03.000000000 -04:00
categories:
- ruby
tags: []
comments: []
---
My answer : get Python! Someone wrote a handy program in Python that helps you out:
http://ntlmaps.sourceforge.net/
1) Download
2) change the configuration file (most likely just enter your username and password)
3) double-click on runserver.bat
4) make sure one of your environmental variables is http_proxy = http://localhost:5865 and the other one ftp_proxy = ftp://localhost:5865
5) use rubygems

Of course, if someone were to rewrite it in Ruby.. ;-)

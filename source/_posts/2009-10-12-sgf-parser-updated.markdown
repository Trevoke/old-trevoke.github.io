---
layout: post
status: publish
published: true
title: SGF Parser updated
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 168
wordpress_url: http://trevoke.net/blog/?p=168
date: 2009-10-12 13:04:02.000000000 -04:00
categories:
- ruby
- weiqi
tags:
- ruby
- sgf
- weiqi
- sgfparser
comments: []
---
Someday I'll come out with a proper revision numbering scheme for it.
I've implemented some <a href="http://cukes.info/">Cucumber</a> testing, the code now <em>actually</em> parses SGF files properly, including the KGS ones, it'll work on Ruby 1.8.6, 1.8.7, 1.9.1, so .. It's all good on that front.

The code's not as clean as I'd like it to be, and probably not as commented, either.
http://github.com/Trevoke/SGFParser

I am not -saving- SGF files with it yet, but heck if I'm not parsing them. And now YOU can, too !

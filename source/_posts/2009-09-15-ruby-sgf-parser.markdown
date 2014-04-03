---
layout: post
status: publish
published: true
title: Ruby SGF Parser
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 148
wordpress_url: http://trevoke.net/blog/?p=148
date: 2009-09-15 23:20:17.000000000 -04:00
categories:
- ruby
- programming
- weiqi
tags:
- ruby
- sgf
- weiqi
- go
comments: []
---
So, I play weiqi (known as the game of go, but I prefer using the chinese name).
There are some SGF parsers out there for Ruby, but I wanted to write my own - the other ones didn't seem comprehensive enough, didn't seem Ruby-like enough in their objectifiying the <del datetime="2009-09-16T04:15:45+00:00">women</del> data.
My original goal was twofold: write a script to rename all the SGF files in my collection so they can be easily parsed later, and ... Learn more Ruby!
Here is the github link: http://github.com/Trevoke/SGFParser
It's a work in progress. Right now it parses the SGF file properly, but the user has a fair amount of work to do to use the data.. Which, maybe, is the way it needs to be. But I'm gonna try to follow the principle of least surprise to the bitter end! :)

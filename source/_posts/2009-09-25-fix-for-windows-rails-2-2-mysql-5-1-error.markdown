---
layout: post
status: publish
published: true
title: Fix for Windows + Rails 2.2 + Mysql 5.1 = error
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 160
wordpress_url: http://trevoke.net/blog/?p=160
date: 2009-09-25 09:58:28.000000000 -04:00
categories:
- rails
- databases
tags:
- mysql
- rails
- windows
comments:
- id: 21
  author: ptecca
  author_email: paul.tecca@comcast.net
  author_url: ''
  date: '2009-10-04 22:22:04 -0400'
  date_gmt: '2009-10-05 03:22:04 -0400'
  content: Thank you!  I hit this same problem and was struggling to solve it until
    I found your post.
---
If you get this error : <em>Mysql::Error: query: not connected:</em> or one just like it, it's because you need an older DLL.. Which I just happen to have found, because I needed to fix this problem too!
<a href="http://trevoke.net/blog/wp-content/uploads/2009/09/libmySQL.dll">libmySQL.dll</a>

Enjoy.

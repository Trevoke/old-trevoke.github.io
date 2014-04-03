---
layout: post
status: publish
published: true
title: Installing the mysql gem on OSX
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 103
wordpress_url: http://trevoke.net/blog/?p=103
date: 2009-04-17 22:25:44.000000000 -04:00
categories:
- ruby
tags:
- ruby
- gems
- osx
- mysql
comments: []
---
Taken straight from <a href="http://www.eclips3media.com/workshop/2008/10/installing-the-mysql-gem-on-os-x/">this blog</a>

in a terminal.. First do a 'locate mysql_config' and then replace the path in the following command with where that file is.

$ sudo gem install mysql -- --with-mysql-config=/usr/local/mysql/bin/mysql_config
Building native extensions.  This could take a while...
Successfully installed mysql-2.7
1 gem installed

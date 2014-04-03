---
layout: post
status: publish
published: true
title: Ruby on Rails + Sybase
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 125
wordpress_url: http://trevoke.net/blog/2009/07/31/ruby-on-rails-sybase/
date: 2009-07-31 09:32:27.000000000 -04:00
categories:
- databases
tags:
- ruby
- rails
- sybase
comments: []
---
Caveat: This adapter may only work with the enterprise edition of Sybase (i.e. Sybase ASE) not with SQLAnywhere (Sybase ASA)

gem install activerecord-sybase-adapter -s http://gems.rubyonrails.org

ActiveRecord::Base.establish_connection(
:adapter => "sybase",
:database => "test", 
:host => "www.yourdbserver.com",
:username => "kevin", 
:password => "test")

Play!

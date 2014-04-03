---
layout: post
status: publish
published: true
title: installing redcar 0.1 on Gentoo Linux (failed)
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
excerpt: 'redcar is a text-editor for Ruby written in Ruby and Vala. 0.1 is out -
  Conclusion: doesn''t work if 1.9 is installed.'
wordpress_id: 107
wordpress_url: http://trevoke.net/blog/?p=107
date: 2009-04-21 21:40:24.000000000 -04:00
categories:
- ruby
tags:
- ruby
comments: []
---
This tutorial may be incomplete - I set this up from my system, which already has a lot of libraries and packages installed. The readme recommends glib, gtk, gtksourceview2 and such - YMMV.. This is what -I- had to do.
# eselect ruby set ruby18
# layman -S
# layman -a gnome

(if you are running on amd64)
# echo "dev-libs/libgee ~amd64" >> /etc/portage/package.keywords/common
# echo "dev-lang/vala ~amd64" >> /etc/portage/package.keywords/common

# emerge dev-libs/oniguruma dev-libs/libgee ruby-gnome2


AND HERE'S WHERE IT BIT IT. I couldn't build ruby-gdkpixbuf2 against Ruby19 and I didn't feel like uninstall Ruby19.


# gem install oniguruma activesupport rspec cucumber hoe open4 zerenity

I guess I'll have to wait a little longer for this machine. I do have an old laptop running Ubuntu - and redcar gives detailed Ubuntu installation instructions.

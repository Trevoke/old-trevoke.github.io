---
layout: post
status: publish
published: true
title: 'New gem: ListBrowser'
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 209
wordpress_url: http://trevoke.net/blog/?p=209
date: 2010-01-15 19:01:19.000000000 -05:00
categories:
- ruby
tags:
- ruby
- gem
- listbrowser
comments: []
---
~~~~ ListBrowser README ~~~~

I was working on a parser for a very specific tree structure, and was frustrated that there wasn’t a simple way to parse it in irb. "What??", I thought. "I have to use my brain?! God forbid!". So I set to using my brain a little more to create this tool. It’s not much, but maybe it’ll make someone’s life a little easier.

Install: (set up gemcutter)
gem install ListBrowser

It can be used in irb, and really should be used there - when you call it on a tree structure, you’ll get a menu with a list of choices on how you want to go through whatever structure you gave it.

In my particular, special case, I would do something like this:

require ‘sgf_parser’ # For my tree structure require ‘list_browser’ # For this.

tree = SgfParser::Tree.new :filename => "kogo.sgf"

ListBrowser.new tree.root, ‘parent’, ‘children’, ‘properties’

# And follow the menu!

 In my particular case, I would not need to enter those strings, as they
 just happen to be the names I chose for my tree structure, but they should
 serve as a good enough example!

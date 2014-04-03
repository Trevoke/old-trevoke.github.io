---
layout: post
status: publish
published: true
title: Rails, HAML, alternatible CSS for tables
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 132
wordpress_url: http://trevoke.net/blog/?p=132
date: 2009-09-02 11:31:32.000000000 -04:00
categories:
- rails
tags: []
comments: []
---
If you've done any kind of table display in Rails, you've probably discovered the useful 'cycle' method:

<tr class="<%= cycle("even", "odd") %>">

This works after you've set two CSS classes between which you want to alternate - in my example, even and odd, because I have such amazing imagination. Come to think of it, to make my code more readable, it should be 'lightbg' and 'darkbg', or something similar. I'll fix that.

But yeah - how do you do that in HAML?
Piece of CAKE (in this case, it is not a lie).

%tr{:class => cycle('even', 'odd') }</tr>

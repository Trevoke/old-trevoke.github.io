---
layout: post
status: publish
published: true
title: On re-reading old code
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 185
wordpress_url: http://trevoke.net/blog/?p=185
date: 2009-12-09 12:07:51.000000000 -05:00
categories:
- ruby
tags: []
comments: []
---
I came across this beauty:

[ruby]def same_modality? list
  check = list[0][0]
  list.each do |i|
    return false if check != i[0]
  end
  return true
end[/ruby]
This was "necessary" because I got an array of one-element arrays back, and I wanted to check whether or not that one element was the same across the array.

Three seconds of thinking made me realize that just maybe, I could do this:
[ruby]list.uniq.size == 1[/ruby]

I -like- Ruby.

---
layout: post
status: publish
published: true
title: "(Lexicographic) Permutations in Ruby"
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 42
wordpress_url: http://trevoke.net/blog/?p=42
date: 2008-12-20 21:13:19.000000000 -05:00
categories:
- food for thought
- ruby
tags:
- ruby
- permutations
comments:
- id: 26
  author: Inter-array permutations in Ruby | Seven steps
  author_email: ''
  author_url: http://trevoke.net/blog/2009/12/17/inter-array-permutations-in-ruby/
  date: '2009-12-17 12:51:15 -0500'
  date_gmt: '2009-12-17 17:51:15 -0500'
  content: "[...] completely clean, but it works. I had, almost a year ago (362 days
    ago), written a blog post about lexicographic permutations. That was about permutations
    of elements within one array. Someone on ruby-forum asked about [...]"
---
Taking the code from <a title="Permutations in Ruby and Python" href="http://abachman.disqus.com/simple_permutations_in_python_and_ruby/" target="_blank">this other blog</a> ... It's pretty elegant Ruby!

I won't waste your time repeating what the guy wrote in his blog - you're welcome to go read it. I just felt that I should help spread a little this elegant implementation of the standard permutation algorithm, fixing a small bug within it in the process. If, like me, you have issues understanding how to use this, well - you have to use this function and call a block of code on it. It runs the block of code on each permutation it finds.

[sourcecode language="ruby"]def permutations array
  if array.size &lt; 2
    yield array
  else
    array.each do |element|
      permutations(array.select() {|n| n != element}) \
      {|val| yield([element].concat val)}
    end
  end
end[/sourcecode]

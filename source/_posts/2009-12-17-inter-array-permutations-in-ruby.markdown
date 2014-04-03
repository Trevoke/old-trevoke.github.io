---
layout: post
status: publish
published: true
title: Inter-array permutations in Ruby
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 193
wordpress_url: http://trevoke.net/blog/?p=193
date: 2009-12-17 12:51:06.000000000 -05:00
categories:
- food for thought
- ruby
tags:
- ruby
- permutations
- algorithm
comments:
- id: 64
  author: timblair
  author_email: tim@bla.ir
  author_url: ''
  date: '2013-05-23 06:13:09 -0400'
  date_gmt: '2013-05-23 11:13:09 -0400'
  content: "There's no need for an intermediary function: you can just use Array#product
    directly to do everything for you:\r\n\r\n    [1,2].product([3,4], [5]).map {
    |a| a.join(\", \") }   #=&gt; [\"1, 3, 5\", \"1, 4, 5\", \"2, 3, 5\", \"2, 4,
    5\"]"
- id: 65
  author: Trevoke
  author_email: trevoke@gmail.com
  author_url: http://trevoke.net
  date: '2013-05-27 20:14:33 -0400'
  date_gmt: '2013-05-28 01:14:33 -0400'
  content: Hah, cool! Thanks.
---
I don't really have a better name for this. It's also not completely clean, but it works. I had, almost a year ago (362 days ago), written a blog post about <a href="http://trevoke.net/blog/2008/12/20/lexicographic-permutations-in-ruby">lexicographic permutations</a>. That was about permutations of elements within one array.
Someone on ruby-forum asked about permutations between multiple arrays. I <a href="http://stackoverflow.com/questions/710670/c-permutation-of-an-array-of-arraylists">found something in C#</a>, which I was happy to transcribe to Ruby and tweak a little.

{% highlight ruby %}
def array_permutations array, index=0
  # index is 0 by default : start at the beginning, more elegant.
  return array[-1] if index == array.size - 1 # Return last element if at end.
  result = []
  array[index].each do |element| # For each array
    array_permutations(array, index + 1).each do |x| # Permute permute permute
      result &lt;&lt; &quot;#{element}, #{x}&quot;
    end
  end
  return result
end
{% endhighlight %}

So, we get this:
{% highlight ruby %}
first = ['one', 'two']
second = ['three', 'four']
third = 'five', 'six']
result = array_permutations [first, second, third]
=> ['one, three, five', 'one, three, six', 'one, four, five', 'one, four, six',
   'two, three, five', 'two, three, six', 'two, four, five', 'two, four, six']
{% endhighlight %}

Magic!

------
Edit - of course, my solution is hackish, and someone came up with a quicker and more elegant solution:

{% highlight ruby %}
def fancy_array_permutation array
  return array[0] if array.size == 1
  first = array.shift
  return first.product( fancy_array_permutation(array) ).map {|x| x.flatten.join(' ')}
end
{% endhighlight %}

This gives the same result as above.

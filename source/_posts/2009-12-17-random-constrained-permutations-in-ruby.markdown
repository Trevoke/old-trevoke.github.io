---
layout: post
status: publish
published: true
title: Random constrained permutations in Ruby
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 199
wordpress_url: http://trevoke.net/blog/?p=199
date: 2009-12-17 13:50:20.000000000 -05:00
categories:
- ruby
tags:
- ruby
- permutations
- algorithms
comments: []
---
Look, Ma, these are my baby steps in algorithms!

[ruby]# list is the elements to be permuted
# y is the number of results desired
# z is the number of elements per result
# equalizer keeps track of who got used how many times
def constrained_permutations list, y, z
  list.uniq! # Never trust the user. We want no repetitions.
  equalizer = {}
  list.each { |element| equalizer[element] = 0 }

  results = []
  # Do this until we get as many results as desired
  while results.size &lt; y
    pool = []
    puts pool
    least_used = equalizer.each_value.min
    # Find how used the least used element was
    while pool.size &lt; z
      # Do this until we have enough elements in this resultset
      element = nil
      while element.nil?
        # If we run out of &quot;least used elements&quot;, then we need to increment
        # our definition of &quot;least used&quot; by 1 and keep going.
        element = list.shuffle.find do |x|
          !pool.include?(x) &amp;&amp; equalizer[x] == least_used
        end
        least_used += 1 if element.nil?
      end
      equalizer[element] += 1
      # This element has now been used one more time.
      pool &lt;&lt; element
    end
    results &lt;&lt; pool
  end
  return results
end

constrained_permutations [0,1,2,3,4,5,6], 6, 2
=&gt; [[4, 0], [1, 3], [2, 5], [6, 0], [2, 5], [3, 6]]
constrained_permutations [0,1,2,3,4,5,6], 6, 2
=&gt; [[4, 5], [6, 3], [0, 2], [1, 6], [5, 4], [3, 0]]
[/ruby]


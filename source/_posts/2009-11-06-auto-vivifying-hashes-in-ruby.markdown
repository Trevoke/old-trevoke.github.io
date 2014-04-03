---
layout: post
status: publish
published: true
title: Auto-vivifying hashes in Ruby
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 178
wordpress_url: http://trevoke.net/blog/?p=178
date: 2009-11-06 08:27:09.000000000 -05:00
categories:
- ruby
tags:
- ruby
comments:
- id: 28
  author: swhirsch
  author_email: swhirsch@nyc.rr.com
  author_url: ''
  date: '2010-02-15 09:42:00 -0500'
  date_gmt: '2010-02-15 14:42:00 -0500'
  content: careful!  These DO NOT work as they do in perl.
- id: 29
  author: Trevoke
  author_email: aldric@trevoke.net
  author_url: http://trevoke.net
  date: '2010-02-15 14:34:53 -0500'
  date_gmt: '2010-02-15 19:34:53 -0500'
  content: How -do- they work in Perl ?
---
An auto-vivifying hash is a hash that lets you create sub-hashes automatically. This means that the following code becomes possible:

[code]def cnh # silly name &quot;create nested hash&quot;
  Hash.new {|h,k| h[k] = Hash.new(&amp;h.default_proc)}
end
my_hash = cnh
my_hash[1][2][3] = 4
my_hash # =&gt; { 1 =&gt; { 2 =&gt; { 3 =&gt;4 } } }
[/code]

This is useful because it reduces the amount of logic in the code. No more "If sub-hash doesn't exist, create it!"

Courtesy of Robert Klemme on www.ruby-forum.com

_____

Update:

Facets has a way of doing an auto-vivifying hash, too! Thanks to <a href="http://stackoverflow.com/questions/1503671/ruby-hash-autovivification-facets">Stackoverflow</a>.
<div>
<div>[code]
# Monkey patching Hash class:
# File lib/core/facets/hash/autonew.rb, line 19
  def self.autonew(*args)
    leet = lambda { |hsh, key| hsh[key] = new( &amp;leet ) }
    new(*args,&amp;leet)
  end
[/code]

</div>
</div>
<div>
<div>
<div>

The standard <a rel="nofollow" href="http://ruby-doc.org/core/classes/Hash.html#M002840">new  method for Hash</a> accepts a block. This block is called in the event  of trying to access a key in the Hash which does not exist. The block is  passed the Hash itself and the key that was requested (the two  parameters) and should return the value that should be returned for the  requested key.

You will notice that the <code>leet</code> lambda does 2 things. It  returns a new Hash with <code>leet</code> itself as the block for  handling defaults. This is the behaviour which allows <code>autonew</code> to work for Hashes of arbitrary depth. It also assigns this new Hash to  <code>hsh[key]</code> so that next time you request the same key you  will get the existing Hash rather than a new one being created.

Sweet deal!

</div>
</div>
</div>

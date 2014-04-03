---
layout: post
status: publish
published: true
title: Fix to rubyscript2exe / tar2rubyscript
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 99
wordpress_url: http://trevoke.net/blog/?p=99
date: 2009-04-06 15:27:14.000000000 -04:00
categories:
- ruby
tags:
- ruby
- rubyscript2exe
- tar2rubyscript
comments:
- id: 7
  author: cowlibob
  author_email: james@cowlibob.co.uk
  author_url: ''
  date: '2009-06-04 05:25:40 -0400'
  date_gmt: '2009-06-04 10:25:40 -0400'
  content: "I've had mixed results with this. It seems that $0.size is important;
    if the new value is a longer string, it will be truncated. \r\n\r\nThis would
    explain the posters on ruby-talk who saw no output after applying the  'Higgs
    Bozo' fix.\r\n\r\nI've yet to find a _proper_ fix, but modifying the temp path
    name earlier in the code has helped in my instance."
- id: 8
  author: Trevoke
  author_email: aldric@trevoke.net
  author_url: http://trevoke.net
  date: '2009-06-05 19:06:17 -0400'
  date_gmt: '2009-06-06 00:06:17 -0400'
  content: The temp path name - where is that in the code?
- id: 9
  author: cowlibob
  author_email: james@cowlibob.co.uk
  author_url: ''
  date: '2009-06-06 15:53:06 -0400'
  date_gmt: '2009-06-06 20:53:06 -0400'
  content: "I've since found a better fix, to alias $0 to another global string, which
    is then assigned File.expand_path(\"./init.rb\"). \r\n\r\nSee http://gtihub.com/cowlibob/rubyscript2exe
    for the explanation and fixed script.\r\n\r\nHope that's of help."
- id: 10
  author: cowlibob
  author_email: james@cowlibob.co.uk
  author_url: ''
  date: '2009-06-06 15:59:50 -0400'
  date_gmt: '2009-06-06 20:59:50 -0400'
  content: 'Sorry, typo: that should be http://github.com/cowlibob/rubyscript2exe'
---
UPDATE!
Cowlibob did a fix, find it at  : http://github.com/cowlibob/rubyscript2exe


Untested!
From 'The Higgs bozo' on the ruby newsgroup. Apply change to both rubyscript2exe and tar2rubyscript. As far as I know that makes it work with newer versions of Ruby but I didn't get to play with it yet.

--- rubyscript2exe.rb.orig      2009-04-03 10:28:41.140806000 -0400
+++ rubyscript2exe.rb   2009-04-03 10:29:40.108423800 -0400
@@ -618,7 +618,7 @@

   newlocation do
     if __FILE__ == $0
-      $0.replace(File.expand_path("./init.rb"))
+      $0 = File.expand_path("./init.rb")

       TAR2RUBYSCRIPT   = true  unless defined?(TAR2RUBYSCRIPT)

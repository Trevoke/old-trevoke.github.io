---
layout: post
status: publish
published: true
title: Grouping directories by name
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 71
wordpress_url: http://trevoke.net/blog/?p=71
date: 2009-01-27 14:20:43.000000000 -05:00
categories:
- ruby
tags:
- ruby
comments: []
---
As is, this code will create an array of arrays - Directories with the same 6 first characters will be grouped in the same sub-array. I am using this for log directories, name format 20081125 for instance - you can just replace the logic to be whatever you need, of course.

[sourcecode]dirs = []
Dir['*'].each do |item| 
  if File.directory?(item)
    if dirs.empty?
      dirs << [item]
      next
    end
    inserted = false
    dirs.each_with_index do |list_of_folders, index|
      if list_of_folders[0].to_s[0..5] == item[0..5]
        dirs[index] << item
        inserted = true
      end
    end
    dirs << [item] if !inserted
  end
end[/sourcecode]

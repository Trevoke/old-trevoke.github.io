---
layout: post
status: publish
published: true
title: How to delete all files older than a day recursively in a directory and its
  subdirectories
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 14
wordpress_url: http://trevoke.net/blog/2008/11/04/how-to-delete-all-files-older-than-a-day-recursively-in-a-directory-and-its-subdirectories/
date: 2008-11-04 14:20:45.000000000 -05:00
categories:
- technology
- ruby
tags:
- ruby
- delete
- recursive
comments: []
---
Whoo! I haven't done a post that long in a while! Also makes me think I should get a wordpress plugin for some 'code' tags..

I put 'activerecord' in there to take advantage of the '24.hours.ago' notation, which makes life much easier. The cost is a little less than 2 seconds to load the library, so I think it's worth it. It runs as a daily job before backup to tape, to clear old backups from the directory tree.

[sourcecode language='ruby']require 'activerecord'

def delete_recursively(in_here)
  Dir.chdir(in_here)
  Dir.glob('*') do |filename|
    if File.directory?(filename)
      delete_recursively(filename)
      else
        if File.mtime(filename) > 24.hours.ago
        File.delete(filename)
      end
    end
  end
Dir.chdir('..')
end

delete_recursively("your/path/here")[/sourcecode]

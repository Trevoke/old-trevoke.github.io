---
layout: post
status: publish
published: true
title: Grepping a single file for 'dynamic' content
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 294
wordpress_url: http://trevoke.net/blog/?p=294
date: 2011-08-31 14:22:14.000000000 -04:00
categories:
- Uncategorized
tags:
- linux
- xargs
- grep
- bash
comments: []
---
You can use xargs to grep the same word through different files. But how do you use xargs to grep different words through the same file?
Like this:

echo "your fancy word finder stuff here" | xargs -i bash -c 'grep -n "{}" your/file/here'

Not something that's useful every day, but when you want it, hot damn is it nice to have.

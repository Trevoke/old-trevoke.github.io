---
layout: post
status: publish
published: true
title: Add a user to the wheel group in OSX
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 376
wordpress_url: http://trevoke.net/blog/?p=376
date: 2013-02-07 10:46:25.000000000 -05:00
categories:
- osx
tags:
- osx
- wheel
- groups
comments: []
---
Why are these things always so weird? Someday I'll understand why OSX is set up that way. And on that day, I'll probably weep.
<blockquote>$ sudo /usr/bin/dscl . -append /groups/wheel GroupMembership <em>username</em>
<p style="padding-left: 30px;"></p>
</blockquote>
This was found here : https://discussions.apple.com/thread/1230828?start=0&amp;tstart=0

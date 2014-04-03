---
layout: post
status: publish
published: true
title: 'Gentoo Prefix on Lion: gettext problem'
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 290
wordpress_url: http://trevoke.net/blog/?p=290
date: 2011-08-08 23:04:18.000000000 -04:00
categories:
- Uncategorized
tags:
- osx
- Gentoo
- lion
- gettext
comments: []
---
So, you can't install gettext?
Here's a hack to get you past it.
do your
$ emerge --oneshot gettext

When it's all unpacked, Ctrl+z (this will pause the job), go to the work directory, something like this:
/Users/you/Gentoo/var/tmp/portage/sys-devel/gettext-0.18.1.1-r2/work/gettext-0.18.1.1

From there, go in here:
cd gettext-tools/gnulib-lib
and in here..

edit "stpncpy.c" with your favorite text editor, find 
"# define __stpncpy stpncpy"
And add // at the beginning of the line, like so:
"//# define __stpncpy stpncpy"

Save and quit, then type "fg 1" and return, this will resume the job.

This hack bypasses the stpncpy problem. Someone more serious than me needs to create a new ebuild for this though...

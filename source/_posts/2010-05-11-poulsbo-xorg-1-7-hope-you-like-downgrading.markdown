---
layout: post
status: publish
published: true
title: Poulsbo + Xorg 1.7 = (Hope you like downgrading)
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 244
wordpress_url: http://trevoke.net/blog/?p=244
date: 2010-05-11 15:52:46.000000000 -04:00
categories:
- technology
- Gentoo
tags:
- Gentoo
- poulsbo
- psb
- x.org
comments:
- id: 46
  author: Amit Agarwal
  author_email: ''
  author_url: http://blog.amit-agarwal.co.in/2010/06/22/fixing-xorg-server-removing-nouveau-nvidia-installing-nvidia-graphics-card/
  date: '2010-06-21 22:24:19 -0400'
  date_gmt: '2010-06-22 03:24:19 -0400'
  content: |-
    <strong>Fixing the Xorg X server after removing nouveau and nvidia and installing a nVidia graphics card....</strong>

    I found your entry interesting thus I've added a Trackback to it on my weblog :)...
---
If you happen to use Gentoo on a Notebook, you may already know this. If not..

At the time of this writing, If you have a Poulsbo video card (another craptastic Intel invention) do _not_ upgrade to xorg-server 1.7. Stay on 1.6.5-r1 or whatever you have. If you upgrade, xorg will just refuse to work for you, and downgrading is kind of a pain.

If you have upgraded already, then here's what to do:

http://bugs.gentoo.org/show_bug.cgi?id=290679#c4

After doing this, you'll need to also mask &gt;xorg-server-1.6.5-r1, then re-install the old xorg-server, and finally re-emerge everything you have installed from the category x11-drivers.

Have fun!

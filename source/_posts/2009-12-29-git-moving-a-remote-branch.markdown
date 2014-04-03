---
layout: post
status: publish
published: true
title: 'Git : moving a remote branch'
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 204
wordpress_url: http://trevoke.net/blog/?p=204
date: 2009-12-29 17:08:43.000000000 -05:00
categories:
- programming
tags:
- git
- branch
- move
comments: []
---
One can't actually move a remote branch, but you can copy a branch and delete a branch, so...

Copy oldbranch in repo to newbranch.
[code]git push {repo} {oldbranch}:heads/{newbranch}[/code]
Ex: git push origin foobranch:barbranch
renames foobranch to barbranch

Remove a remote branch: it’s all about the colon:

[code]git push &lt;remote_repo&gt; :heads/&lt;branch&gt;[/code]

Example: git push origin :heads/some-branch removes some-branch from the remote repo (apparently git push origin :some-branch works as well).

This works for removing a tag as well: git push origin :sometag

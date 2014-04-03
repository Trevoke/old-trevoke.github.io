---
layout: post
status: publish
published: true
title: 'Devise + rspec error: undefined method ''name'''
author: Trevoke
author_login: Trevoke
author_email: trevoke@gmail.com
author_url: http://trevoke.net
wordpress_id: 334
wordpress_url: http://trevoke.net/blog/?p=334
date: 2012-06-11 10:14:58.000000000 -04:00
categories:
- ruby
- rails
- programming
tags:
- ruby
- rspec
- rails 3
- devise
comments: []
---
If you're using Devise and rspec on Rails 3, and you want to override a controller, and you end up with an error that makes no sense whatsoever:

`Undefined method 'name' for nil:NilClass`, well then, you probably want to add the following line to your tests:

``` ruby linenos:false
@request.env["devise.mapping"] = Devise.mappings[:admin]
```
Yeah... That took me way longer than expected.

On a COMPLETELY UNRELATED SIDE NOTE, pry is pretty cool when you end up having to step through code...

---
author: yoavshapira
comments: true
date: 2009-03-18 15:13:00+00:00
layout: post
link: http://blog.yoavshapira.com/2009/03/18/converting-character-sets-efficiently-in-mysql/
slug: converting-character-sets-efficiently-in-mysql
title: Converting character sets (efficiently) in MySQL
wordpress_id: 1843
---

As part of this morning's RSS reading run, I came across [this gem](http://www.mysqlperformanceblog.com/2009/03/17/converting-character-sets/) from the folks at Percona.  Their "[MySQL Performance Blog](http://www.mysqlperformanceblog.com/)" in general is very good, and [this entry](http://www.mysqlperformanceblog.com/2009/03/17/converting-character-sets/) is no exception.  It talks about how to save and even parallelize database operations while converting a table or database charset from whatever to UTF-8.

  


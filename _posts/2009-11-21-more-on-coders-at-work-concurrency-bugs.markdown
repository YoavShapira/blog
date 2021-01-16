---
author: yoavshapira
comments: true
date: 2009-11-21 18:32:00+00:00
layout: post
link: http://blog.yoavshapira.com/2009/11/21/more-on-coders-at-work-concurrency-bugs/
slug: more-on-coders-at-work-concurrency-bugs
title: 'More on Coders at work: concurrency bugs'
wordpress_id: 1632
categories:
- Blogger
- books
---

If you're looking for [my first / basic review of Coders at Work, it's here](http://yoavs.blogspot.com/2009/11/book-review-coders-at-work.html).  Highly recommended.  
  
In the book, Peter Seibel asks each programmer what's the worst bug they've had to deal with.  Many of the answers are concurrency bugs.  Issues related to multi-threaded applications running many things at once.  
  
This makes complete sense.  It's been my experience as well.  Those concurrency bugs are really annoying.  
  
At [HubSpot](http://dev.hubspot.com), we have one guy, Drew, who is just awesome at ironing these out on the Java side of things.  He not only knows the underlying libraries and their pitfalls really well, but he has a knack for thinking about concurrency issues.  It's a really valuable talent.  
  
Thankfully, we don't have to delve into low-level C code and [gdb](http://www.gnu.org/software/gdb/) to debug a lot of our issues.  The programmers in this book often had to do that.  And that, by itself, is a good reason for [giving thanks](http://en.wikipedia.org/wiki/Thanksgiving).

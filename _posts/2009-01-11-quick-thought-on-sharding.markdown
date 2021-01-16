---
author: yoavshapira
comments: true
date: 2009-01-11 12:47:00+00:00
layout: post
link: http://blog.yoavshapira.com/2009/01/11/quick-thought-on-sharding/
slug: quick-thought-on-sharding
title: Quick thought on sharding
wordpress_id: 1888
---

Like many readers of this blog, I made my way though blog post links to [the 37Signals post last week about sharding](http://www.37signals.com/svn/posts/1509-mr-moore-gets-to-punt-on-sharding).  Or rather, not sharding, but growing the central servers bigger and bigger with more RAM, so you can cache everything.

  


It's certainly a very interesting post, and it generated good discussion.  I like [DHH](http://www.loudthinking.com/about.html) and he's obviously a smart guy.  Plus he's got a good writing style, which distinguishes him from many engineers.  But I disagree with his main point.  Here's why:

  


(1) It's true [Moore's Law](http://en.wikipedia.org/wiki/Moore's_law) is awesome, and it's our friend and all.  But for many applications, the volume of data they need to deal with is growing far faster than Moore's Law.  So waiting for another N months for the next doubling in size of RAM is not a good idea.  You'll run out of space and end up hitting the disk, which is the bottleneck (as he noted).

  


(2) Even if you could keep up with huge memory servers, one is not enough.  You still need a backup / failover, at least one, if you want any reasonable uptime.  That would get expensive.  What's more, you probably have to upgrade them at or around the same time because it would not do well to have a 256GB main server and a 128GB backup for a long time.

  


(3) As DHH and others, e.g. [Cal Henderson](http://www.iamcal.com/) (Flickr guy, [great book](http://www.amazon.com/exec/obidos/ASIN/0596102356)) note, the real bottleneck is on I/O writes.  For reads, we have a bunch of cool solutions even without sharding, e.g. memcached.  Super-fast drives like the [Fusion I/O](http://www.fusionio.com/) DHH mentions are expensive, not easily available, and won't fit a lot server motherboards.  They're definitely nice shiny toys, though ;)

  


(4) When you start relying on exotic low-level pieces, like special I/O cards and special memory, you start going into [driver hell](http://www.google.com/search?rlz=1C1GGLS_en-USUS291US304&sourceid=chrome&ie=UTF-8&q=driver+hell).  You might need special patched kernels, drivers, and peripherals.  It becomes a bit more of a pain to setup and debug.  It just feels a little more fragile and a little more like the mainframe era.  Maybe that's OK because you have far fewer of these servers to manage.

  


(5) The unknown future.  My favorite thing about designing with large clusters of commodity boxes that we assume they'll fail, and we architect for it a-priori.  I don't know how they'll fail, but I know they'll fail, and I can make the system more robust with this knowledge.  Maybe I'm a little jaded, but I just don't always trust the specs on shiny cutting-edge low-level hardware, in terms of reliability and uptime.

  


I think DHH makes a very interesting, thought-provoking argument.  I just don't fully agree with it.  I wish he'd shared a little more details about their setup with respect to failover, backups, server management, actual database size, etc.

  


If you read a little bit further down [in the comments](http://www.37signals.com/svn/posts/1509-mr-moore-gets-to-punt-on-sharding#), though, he clarifies his position, in what I think makes a lot more sense:

  


<blockquote>I absolutely agree that if you’re Yahoo or Flickr or LiveJournal, you’ll need to shard sooner rather than later. But bear in mind that neither Flickr or LiveJournal started life as a fully sharded application. When did they start sharding? When they needed to!
> 
> That’s generally a good approach to all scaling techniques. Do them when you need to. That doesn’t have to mean “the day everything goes up in smoke”. It can well just mean “we’re growing the db set at 2GB/month and our queries/sec with X/month, this means that in 4 months we’ll be out of headroom on the current setup—let’s shard!”.
> 
> But thinking that you need to shard ahead of time to Play With The Big Boys is just stupid. Chances are you won’t build an application that’s that hot. And if you should be so lucky, you can deal with the problem then. Just like Flickr and LiveJournal and every big site under the sun did.
> 
> </blockquote>

  


That, I think, is 100% right-on.  At my [favorite internet marketing company](http://www.hubspot.com/), we always try to do things the simplest way possible at first.  [DRY](http://en.wikipedia.org/wiki/Don't_repeat_yourself), [YAGNI](http://en.wikipedia.org/wiki/You_Ain't_Gonna_Need_It), [KISS](http://en.wikipedia.org/wiki/KISS_principle), and all that.  But we're growing fast and in some areas we've already needed to partition the data.  There are other areas in which we'll need to do it soon, so we will.

  


By the way, there's another good sharding article by Dan Pritchtt on [his blog](http://www.addsimplicity.com/adding_simplicity_an_engi/2008/08/shard-lessons.html).  Not as controversial, but probably just as valuable ;)

  


  


  


---
author: yoavshapira
comments: true
date: 2008-10-25 16:51:00+00:00
layout: post
link: http://blog.yoavshapira.com/2008/10/25/facebook-scribe-looks-interesting/
slug: facebook-scribe-looks-interesting
title: Facebook Scribe looks interesting
wordpress_id: 1942
---

Recently I've been thinking that the whole rigamarole with logging levels and appender configuration is a bit of a hang-over.  You can get infinitely prescriptive with "this should be an INFO message, this one is ERROR, etc." but you still end up with a lot of grey areas.

  


You also have a lot of machines with a lot of local log files.  Then you have to adapt or invent tools to combine, merge, sort, and make sense of all these log files, usually also copying them elsewhere.  It's totally feasible, an old problem with great tools to help, but it seems like a hangover.

  


Enter [Facebook's Scribe](http://www.facebook.com/note.php?note_id=32008268919&id=9445547199&index=0), now open-source.

  


Just shuttle all the log file info to one (logical, numerous physical) set of servers in a reliable, fast, async way.  Seems helpful.  Also seems like a useful [KISS](http://en.wikipedia.org/wiki/KISS_principle) improvement, removing the idea of a log level (or "priority") while keeping the widespread notion of a label or "category" which practically all current systems support.  I used to think priority was super-useful, now I think an organization-wide set of pre-defined categories may be better.

  


Seems worth trying.

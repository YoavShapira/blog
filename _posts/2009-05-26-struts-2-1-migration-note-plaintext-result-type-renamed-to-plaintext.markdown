---
author: yoavshapira
comments: true
date: 2009-05-26 14:38:00+00:00
layout: post
link: http://blog.yoavshapira.com/2009/05/26/struts-2-1-migration-note-plaintext-result-type-renamed-to-plaintext/
slug: struts-2-1-migration-note-plaintext-result-type-renamed-to-plaintext
title: 'Struts 2.1 migration note: plaintext result type renamed to plainText'
wordpress_id: 1784
---

We ran into this earlier today.  In Struts 2.1.6, the [plain text result type](http://struts.apache.org/2.1.6/struts2-core/apidocs/org/apache/struts2/dispatcher/PlainTextResult.html) was renamed to plainText, with a capital T.  But the error message tells you "did you mean plaintext?" with a lower-case T, which is confusing.

  


So if you get the error below, just change the result type from plaintext to plainText.

  
  


`Caused by: There is no result type defined for type 'plaintext' mapped with name '*'. Did you mean 'plaintext'? - result`

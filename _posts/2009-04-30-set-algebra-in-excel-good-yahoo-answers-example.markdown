---
author: yoavshapira
comments: true
date: 2009-04-30 01:31:00+00:00
layout: post
link: http://blog.yoavshapira.com/2009/04/29/set-algebra-in-excel-good-yahoo-answers-example/
slug: set-algebra-in-excel-good-yahoo-answers-example
title: Set algebra in Excel -- good Yahoo Answers example
wordpress_id: 1802
---

A specific set algebra question, and how to solve it in Excel, has been bugging me for years.  Literally.  I've asked a bunch of people, and the more advanced Excel warriors have given partial answers.

  


All the answers that get close involve many clicks, and usually manual pivot tables.  Those kind of work but I dislike solutions with so many clicks.

  


So I finally asked on [Yahoo](http://answers.yahoo.com/question/index?qid=20090427145458AAQtqDy) how one does a particular type of [set algebra](http://en.wikipedia.org/wiki/Algebra_of_sets) operation in Excel: inspect column A for all values not in column B, and output those values into column C.  Not very complicated.

  


Chaminda came through right away with a great answer that works for me.  Check it out on Yahoo Answers at [http://answers.yahoo.com/question/index?qid=20090427145458AAQtqDy](http://answers.yahoo.com/question/index?qid=20090427145458AAQtqDy).

  


To repeat the core part:

  


Put in C1 & drag down to C10  
=IF(ISERROR(MATCH (A1,$B$1:$B$10,0)),A1,"")  
  
If you need more info, add details or email me.  
  
ADDED- And if you do not want any empty cells in between, try this.  
  
=IFERROR(INDEX($A$1:$A$10, SMALL(IF(NOT (IFERROR(MATCH ($A$1:$A$10,$B$1:$B$10,0),0)), ROW($A$1:$A$10)),ROW())),"")  


  


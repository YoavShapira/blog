---
author: yoavshapira
comments: true
date: 2008-08-11 15:17:00+00:00
layout: post
link: http://blog.yoavshapira.com/2008/08/11/how-to-install-tidy-2-0-on-fedora-core/
slug: how-to-install-tidy-2-0-on-fedora-core
title: How to install Tidy 2.0 on Fedora Core
wordpress_id: 1998
---

I just finished this installation and ran into a couple of problems, so maybe someone else will benefit.  If you haven't read [the PHP Tidy manual](http://us2.php.net/tidy), you should.  
  
First, install [libtidy](http://tidy.sourceforge.net/) and libtidy-devel.  If you don't install libtidy-devel you will get an error later, during the configure step for the PHP library.  
  
sudo yum install libtidy libtidy-devel  
  
Second, download Tidy 2.0.  Tidy 1.x is what I got via yum, but as the manual says, this is for PHP 4.x.  If you have PHP 5.x, you want Tidy 2.0.  
  
Get it via wget:  
wget -c http://support.office-shadow.com/installer/tidy2.0.tar.gz  
  
(Thank you to whoever runs this site.)  
  
The rest of the instructions are as documented by Paul Maddox at [http://ubuntuforums.org/showthread.php?t=195636](http://ubuntuforums.org/showthread.php?t=195636):  
  

    
    # Unpack the source<br></br>tar xvzf tidy2.0.tar.gz<br></br><br></br># Configure tidy for installed php5 API<br></br>cd tidy<br></br>phpize<br></br><br></br># Configure & Compile the source<br></br>./configure<br></br>make clean    > /etc/php5/apache2/php.ini;

  
Thank you, Paul et al.  
  
Note platform-specific location of the php.ini files.  Mine is actually at /etc/php.ini on Fedora Core.  
  
When this is done, you may need to restart your Apache httpd server.  After you do, the output from phpinfo() should include a subsection labeled DOM with a few lines that say "enabled."

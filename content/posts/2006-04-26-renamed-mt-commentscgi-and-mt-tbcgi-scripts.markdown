---
author: admin
comments: false
date: 2006-04-26 08:30:40+00:00
link: http://habi.gna.ch/2006/04/26/renamed-mt-commentscgi-and-mt-tbcgi-scripts/
slug: renamed-mt-commentscgi-and-mt-tbcgi-scripts
title: renamed mt-comments.cgi and mt-tb.cgi scripts
wordpress_id: 162
categories:
- technospeak
---

yesterday evening chris, the admin of the gna-server informed me that my trackback-scripts stressed the server quite a bit.
  
and because i got a massive hit of spam in the morning (more than 100 spam comments that passed the junk-filter) i decided to do, what i've should have done a long time ago: rename my comment- and trackback-scripts so they cannot be easily guessed remotely.

first, i used the direction posted [here at the photoblogs-wiki](http://wiki.photoblogs.org/wiki/Preventing_Spam) and adapted them a bit:
  
first, i renamed






<blockquote>
...the comment script. A good proportion of comment spam is generated automatically; i.e. a spam site will try to automatically contact your comment script which normally resides at:
  
http://yourURL/cgi-bin/mt-comments.cgi
  
If you rename the script you stop the automatic spam in its tracks. You can rename this file anything you like (e.g. death-to-spambots.cgi) but you a) need to retain the cgi extenstion (I think), and b) also need to make a change to your mt-config.cgi file (which resides in your cgi-bin directory. You need to look for the following block of code
  

  
# CommentScript mt-comments.pl
  
# TrackbackScript mt-tb.pl
  
# SearchScript mt-search.pl
  
# XMLRPCScript mt-xmlrpc.pl
  
# ViewScript mt-view.pl
  

  
... and make two changes. First, uncomment the first line by removing the hash symbol; i.e.
  
CommentScript mt-comments.pl
  
... and second, change the filename to match your renamed version; e.g.
  
CommentScript death-to-spambots.cgi
</blockquote>



<

p>
this means, that the scripts still work, but under another name [1], so noone should be able to just guess their location. but as a human person nothing changes, because you comment through the comment interface and get redirected to the correct script. the problem of this solution is now, that the spammers generate massive amounts of "404: File not found"-errors in the logs, because the original scripts are not there anymore.

to prevent this, i then implemented the Junk slow-down-solution posted [over at the solid wall of code](http://blog.thought-mesh.net/solidwallofcode/movable_type/mt_32_junk_slow.php), which consists of throwing the junk-bots into a loop when they guess the original-file destination.

so if you now go to the original [mt-comments.cgi](http://habi.gna.ch/blog/mt-comments.cgi) on my server, you (or better your spam-script) has to wait 30 seconds before it gets to see an error-message. this should at least slow down the junk scripts and put a bigger burden on the junkers than it does on the server my blog resides on.

[![Mt-Comments](http://habi.gna.ch/blog/images/mt-comments-tm.jpg)](http://habi.gna.ch/blog/images/mt-comments.jpg)the whole setup seems to work quite fine.
  
before renaming the scripts i got around 5 comment spams per minute (!) and now it already has slowed down quite a bit, the last comment spam (as i write it) has been more than 2 hours ago and the one before already four hours ago.
  
see yourself in the screenshot on the left.


[1]: i'm not gonna tell you, leave a comment to see for yourself. :-)




technorati tags: [code](http://www.technorati.com/tag/code), [junk](http://www.technorati.com/tag/junk), [movabletype](http://www.technorati.com/tag/movabletype)



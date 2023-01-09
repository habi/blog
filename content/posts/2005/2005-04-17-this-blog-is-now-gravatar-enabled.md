---
date: 2005-04-17 14:08:50+00:00
link: https://habi.gna.ch/2005/04/17/this-blog-is-now-gravatar-enabled/
slug: this-blog-is-now-gravatar-enabled
title: this blog is now gravatar enabled
wordpress_id: 769
categories:
- technospeak
---


to make posting comments a little bit more rewarding i implemented [gravatars](http://gravatar.com/) on this blog.
  
two days ago i commented on [an entry over at urs' blog](http://www.circle.ch/blog/p1692.html) and some fancy image turned up next to my comment. i've seen that already turning up on different blogs (e.g. [moblg.uk](http://moblog.co.uk/) and [blog.ch](http://blog.ch/blog/index.php/archives/2005/04/15/swiss-blog-awards/#comments)).
  
the code with which i implemented it is shown below for your abuse and modification.


<blockquote>
<MTComments>
  

  
<div class="comments-body">
  
<$MTCommentBody$>
  
<span class="comments-post">
  
<a href="<$MTCommentURL$>">
  
<img src="<$MTGravatar default="https://habi.gna.ch/blank.jpg" size="40"$>" alt="gravatar" align="left" />
  
</a>
  
posted by: <$MTCommentAuthorLink spam_protect="1"$><br />
  
on <$MTCommentDate$><br clear="all">
  
</span>
  
</div>
  

  
</MTComments>
</blockquote>


i made it so that every person gets a gravatar, even it there's none registered (for example, see peters comment [here](https://habi.gna.ch/blog/archives/000568.html)). if your gravatar is missing the pictures gets replaced by [blank.jpg](https://habi.gna.ch/blank.jpg). the gravatar is linked with the url or the (spamsafe) email link of the person that left a comment.
  
so, ladies and gents, if you want your picture to show up in the comments, then step over to gravatar and register yours.
  
thanks, goodbye.


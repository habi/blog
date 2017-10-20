---
author: admin
categories:
- none
comments: true
date: 2004-02-05T20:24:29Z
link: http://habi.gna.ch/2004/02/05/comments-hitparade/
slug: comments-hitparade
title: comments hitparade
url: /2004/02/05/comments-hitparade/
wordpress_id: 434
---

[![](http://habi.gna.ch/blog/images/commentparade-tm.jpg)](http://habi.gna.ch/blog/images/commentparade.jpg)well, after [arni](http://www.arnoldseefeld.com/blog/) posted [some code](http://www.arnoldseefeld.com/blog/archives/000071.html)1 i tried to implement the [comment-hitparade](http://mt-plugins.org/archives/entry/commentleaders.php) i mentioned earlier:
i works nearly like a charm, the only problem is, that my [top commenter](http://www.web-laun.ch/pieceoBlog/index.php) never left an email-address, so he appears as "empty"2
i really start to get the hang of all these [movabletype plugins](http://mt-plugins.org/), a nearly endless resources of things you can do with your blog (i just want to start to use that [blogtimes-thing](http://www.nilesh.org/mt/blogtimes/).
([b.](http://bernhardseefeld.ch/), this is a hint!)

anyways, here's the code:


<blockquote><MTCommentLeaders exclude="habi@gna.ch" lastn="10">
  [<$MTLeaderAuthorLink spam_protect="1"$> (<$MTLeaderCount$>): 
<a href="<$MTBlogArchiveURL$>
<$MTLeaderEntryLink$>#<$MTLeaderCommentID$>">read last.
</a>]<br /></blockquote>



1 i need to get the hang of all that css-stuff! in a week i have a meeting with [abu](http://www.primal.ch/credits/) (marco liniger) concerning some other web-project, he may have some tips.
2 your email is spam-protected (as you can see when you read the code, so start leaving it! i have to group the top-comments by email, if i group it by name then i cannot exclude me and that would be unfair...

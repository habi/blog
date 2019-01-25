---
author: admin
comments: true
date: 2005-11-06 16:57:55+00:00
layout: post
link: http://habi.gna.ch/2005/11/06/comment-feed/
slug: comment-feed
title: comment feed
wordpress_id: 95
categories:
- technospeak
---


[chregu recently mentioned](http://blog.bitflux.ch/archive/2005/11/04/more-latest-comments-feeds.html) that he wants a feed for every blog (actually for every blog software...)
  
so i've modified my already present comment-feed, which i've been using to manage my comments (e.g archive nicely, edit, despam...) into a publicly available format, for all of you to consume.
  
the comment feed can be accessed via this file: [comments.xml](http://habi.gna.ch/blog/comments.xml). 
  
the full code is as follows [1]:





<blockquote><?xml version="1.0" encoding="<$MTPublishCharset$>"?>
  
<rss version="2.0" 
  
xmlns:dc="http://purl.org/dc/elements/1.1/"
  
xmlns:sy="http://purl.org/rss/1.0/modules/syndication/"
  
xmlns:admin="http://webns.net/mvcb/"
  
xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#">
  
<channel>
  
<title><$MTBlogName remove_html="1" encode_xml="1"$> Comments</title>
  
<link><$MTBlogURL$></link>
  
<description>Comments</description>
  
<dc:language>en-us</dc:language>
  
<dc:creator><MTEntries lastn="1"><$MTEntryAuthorEmail$></MTEntries></dc:creator>
  
<dc:date><MTEntries lastn="1"><$MTEntryDate format="%Y-%m-%dT%H:%M:%S"$><$MTBlogTimezone$></MTEntries></dc:date>
  
<admin:generatorAgent rdf:resource="http://www.movabletype.org/?v=<$MTVersion$>" />
  
<sy:updatePeriod>hourly</sy:updatePeriod>
  
<sy:updateFrequency>1</sy:updateFrequency>
  
<sy:updateBase>2000-01-01T12:00+00:00</sy:updateBase>

> 
> 
<MTComments lastn="15" sort_order="descend"><MTCommentEntry>
  
<item>
  
<title><$MTCommentAuthor encode_xml="1"$> on '<$MTEntryTitle encode_xml="1"$>'</title>
  
<link><$MTEntryLink encode_xml="1"$></link>
  
<description>

> 
> 
<![CDATA[
  
<$MTCommentAuthor$> @ <$MTCommentDate format="%d. %B %Y, %H:%M"$>]]><br />
  
(<a href="mailto:<$MTCommentEmail$>">mail</a>, <a href="<$MTCommentURL$>">URL</a>)
  
<br />
  
---<br />
  
<$MTCommentBody encode_xml="1"$>
  
</description>
  
</item>
  
</MTCommentEntry></MTComments>
  
</channel>
  
</rss></blockquote>





so, if you want to add a comment feed to your MT installation, proceed like this. go to your mt.cgi (the main admin), add a new template, give it the name you want (comments.xml works nicely) and paste the code above into the Template Body field.



[1]: didn't code it myself, but forgot where i've gotten it, it's half a century ago (or so...)






technorati tags: [comments](http://www.technorati.com/tag/comments), [feed](http://www.technorati.com/tag/feed), [rss](http://www.technorati.com/tag/rss)

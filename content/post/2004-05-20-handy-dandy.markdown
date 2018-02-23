---
author: admin
categories:
- none
comments: true
date: 2004-05-20T10:47:11Z
link: http://habi.gna.ch/2004/05/20/handy-dandy/
slug: handy-dandy
title: handy dandy!
wordpress_id: 537
---

after submitting a comment spam to the MT-Blacklist, i stopped by at [jayallens blog](http://www.jayallen.org/comment_spam/), and found an interesting link.
[bopuc](http://bopuc.levendis.com/bopuc/archives/-2004/05/14/mt_template_for_monitoring_comment_spam.php) proposes a way to view all the comments on your blog as a rss feed, spruced up with all the relevant links to despam and edit the comment and info of the commenter.
here are the directions:
1. go to your MT-HQ and make a new template. 
call it something you remember and insert a filename for it (e.g. something.xml)
2. paste the code below into the text field.


<blockquote>>
<?xml version="1.0" encoding="<$MTPublishCharset$>"?>
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

<MTComments lastn="15" sort_order="descend"><MTCommentEntry>
<item>
<title><$MTEntryTitle encode_xml="1"$> (<$MTCommentAuthor encode_xml="1"$>)</title>
<link><$MTEntryLink encode_xml="1"$></link>
<description>
<![CDATA[
<a href="http://www.your-domain.com/path/to/your/mt/mt-blacklist.cgi?__mode=despam&_type=comment&id=<$MTCommentID pad="0"$>">DESPAM</a><br />
<a href="http://www.your-domain.com/path/to/your/mt/mt.cgi?__mode=view&_type=entry&id=<MTEntryID>&blog_id=<MTBlogID>">Edit entry</a><br />
<a href="http://www.your-domain.com/path/to/your/mt/mt.cgi?__mode=view&_type=comment&id=<MTCommentID>&blog_id=<MTBlogID>">Edit comment</a><br />
<a href="http://www.your-domain.com/path/to/your/mt/mt-blacklist.cgi?__mode=search&n=50&_type=comment&matchType=ip&ip=<$MTCommentIP$>&re-search=Search"><$MTCommentIP$></a><br />
------------------------------------<br />
<a href="mailto:<$MTCommentEmail$>" title="<$MTCommentEmail$>"><$MTCommentAuthor$></a><br />
<a href="<$MTCommentURL$>"><$MTCommentURL$></a><br />
------------------------------------<br />]]>
<$MTCommentBody encode_xml="1"$>
<![CDATA[------------------------------------<br />
<$MTCommentDate format="%a, %b %d, %Y %H:%M:%S"$>]]>
</description>
</item>
</MTCommentEntry></MTComments>
</channel>
</rss>
</blockquote>


3. rebuild your blog
4. subscribe to the *.xml-file with your favorite rss-reader
5. if you don't like the template, edit it to your likings
6. rub your hands and smile mischievously, as this adds even more fun to stopping comment spam

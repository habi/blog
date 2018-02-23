---
author: admin
categories:
- none
comments: true
date: 2005-01-24T19:54:34Z
link: http://habi.gna.ch/2005/01/24/more-dropdowns/
slug: more-dropdowns
title: more dropdowns
wordpress_id: 722
---

[![Dropdowns](http://habi.gna.ch/blog/images/dropdowns-tm.jpg)](http://habi.gna.ch/blog/images/dropdowns.jpg)thanks to [pete bevin](http://www.petebevin.com/archives/2002/03/12/drop_down_menus.html), my sidebar now sports some more dropdowns. i fiddled with the code he provides on his page, so now it's marginally different. for my MT3 installation the code looks as follows:  

archive dropdown:


<blockquote>
<form>
  
<select onChange="document.location=options[selectedIndex].value;" class="jumpbox">
  
<option value="">monthly archives</option>
  
<MTArchiveList archive_type="Monthly">
  
<option value="<$MTArchiveLink$>"><$MTArchiveTitle$></option>
  
</MTArchiveList>
  
</select>
  
</form>
</blockquote>


comments dropdown:


<blockquote>
<form>
  
<select onChange="document.location=options[selectedIndex].value;" class="jumpbox">
  
<option value="">comment archives</option>
  
<$MTComments lastn="10"$ sort_order="descend">
  
<option value="<$MTBlogArchiveURL$><$MTCommentEntryID pad="1"$>.html"> by <$MTCommentAuthor$>, <? echo datediff2('<$MTCommentDate format="%Y-%m-%d %H:%M:%S"$>'); ?></option>
  
</MTComments>
  
</select>
  
</form>
</blockquote>


recent entries dropdown:


<blockquote>
<form>
  
<select onChange="document.location=options[selectedIndex].value;" class="jumpbox">
  
<option value="">recent entries</option>
  
<MTEntries lastn="10" sort_order="descend">
  
<option value="<$MTEntryPermalink$>"> <$MTEntryTitle$></option>
  
</MTEntries>
  
</select>
  
</form>
</blockquote>


i know the dropdowns don't look nice, but i still need to tweak the css a bit, it just doesn't seem to accept the jumpbox-class. i need to take a deeper look at it. but now i need sleep, that's more important at the moment...
  
how does it look on windows?


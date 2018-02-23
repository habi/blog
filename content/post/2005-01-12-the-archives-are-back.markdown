---
author: admin
categories:
- none
comments: true
date: 2005-01-12T21:59:35Z
link: http://habi.gna.ch/2005/01/12/the-archives-are-back/
slug: the-archives-are-back
title: the archives are back
wordpress_id: 714
---

some time ago i deleted the archives in the sidebar, because the were using up too much screen-realestate. since [people complained](http://blog.ch/blog/index.php/archives/2005/01/11/blogtour-de-suisse-blog/) that my archives are hard to grab, i spent 20 seconds implementing a nice trick posted over at [scriptygoddes](http://www.scriptygoddess.com/): [drop down month archives](http://www.scriptygoddess.com/archives/2003/03/16/drop-down-month-archives/).
  
just paste the code below there where you want your dropdown list to be, rebuild your site and have a go with it.


<blockquote>
<form name="jump2">
  
<select name="myjumpbox" OnChange="document.location=jump2.myjumpbox.options[selectedIndex].value">
  
<option selected>Please Select...</option>
  
<MTArchiveList archive_type="Monthly">
  
<option value="<$MTArchiveLink$>"><$MTArchiveDate format="%B %Y"$></option>
  
</MTArchiveList>
  
</select>
  
</form>
</blockquote>


the code is a simple javascript, so should work in all browsers with fresh flavour, leave a note when not so.
  
and i gotta say this seems to open a lot of possibilities for my sidebar, keep tuned!


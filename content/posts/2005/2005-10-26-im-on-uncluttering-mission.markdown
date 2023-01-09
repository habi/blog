---
comments: true
date: 2005-10-26 12:25:04+00:00
link: https://habi.gna.ch/2005/10/26/im-on-uncluttering-mission/
slug: im-on-uncluttering-mission
title: i'm on uncluttering mission
wordpress_id: 89
categories:
- personal
- pictures
---

i've officially killed my [two](https://habi.bild.li/) [moblogs](http://moblog.co.uk/blogs.php?show=835) [1]. from now on, all my (seldom) moblogging is going to happen here: [https://flickr.com/photos/habi/tags/moblog/](http://flickr.com/photos/habi/tags/moblog/). regarding that, i've also uncluttered my sidebar a bit. the latest images-section now shows the five latest images i posted to flickr. on top there's the latest moblog, then the four latest "normal" images.

i achieved this with a mashup of the code of two [flickr-badges](https://www.flickr.com/badge_new.gne). the first one is pulling just the "moblog" tag, the second one is pulling the last 4 images.

the full code looks like this, nothing too fancy really:

````html
<!-- Start of Flickr Badge -->
<table cellspacing="10" cellpadding="0" border="0">
<script type="text/javascript" src="https://www.flickr.com/badge_code_v2.gne?count=1&amp;display=latest&amp;size=t&amp;layout=v&amp;source=user_tag&amp;user=79112147%40N00&amp;tag=moblog"></p>
<p></script>
<script type="text/javascript" src="https://www.flickr.com/badge_code_v2.gne?count=4&amp;display=latest&amp;size=t&amp;layout=v&amp;source=user&amp;user=79112147%40N00"></p>
<p></script></table>
<!-- End of Flickr Badge -->
````

the code is really straight-forward.

i just cleaned out the css and merged the two javascript parts. if you want to adopt it for your page, you just have to change the user-number and/or tag [2].

[1]: they've been clinically dead anyway...

[2]: a simple google search yielded [this](http://forum.textpattern.com/viewtopic.php?id=7030&p=4): "To get your NSID from Flickr, go to your photos page, view source, find global_nsid, and note the value. That's it."

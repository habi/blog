---
author: admin
comments: true
date: 2005-04-30 18:07:18+00:00
link: http://habi.gna.ch/2005/04/30/technorati-tags/
slug: technorati-tags
title: technorati tags
wordpress_id: 781
categories:
- technospeak
---


oh, and if you're wondering why my tags are not working (e.g see the [tag:emmen](http://www.technorati.com/tag/emmen), which i [pinged some days ago](http://habi.gna.ch/blog/archives/000581.html)): technorati has some problems accessing my site:


<blockquote>
curl -O http://habi.gna.ch/blog/
  
% Total - % Received - % Xferd - Average Speed - Time - Curr. Dload - Upload - Total - Current - Left - Speed
  
0 - 0 - 0 - 0 - 0 - 0 - 0 - 0 - --:--:-- - 0:00:07 - --:--:-- - 0
  
curl: (23) Failed writing body
</blockquote>


after getting in touch with [adriaan](http://ecto.kung-foo.tv/) he found out that the problem is not ecto-based, but more on the technorati site.
  
technorati-support wrote something like:


<blockquote>
maybe he has some kind of referrer blocker or User-Agent blocker that is hosing the spider and curl
</blockquote>


i just love it, when i have no idea what could be b0rked. i guess i misconfigured something with my .htacces-file that helps me with my [image-leechers](http://www.spotleid.de/forum/chilli-con-zert/11706-800.html) and serves them [this image](http://habi.gna.ch/bad.jpeg). i hope b. is able to figure out what went wrong...
  
i'll keep you updated.


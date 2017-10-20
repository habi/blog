---
author: admin
categories:
- technospeak
comments: true
date: 2004-04-01T22:05:28Z
link: http://habi.gna.ch/2004/04/02/itunes-info-in-sidebar/
slug: itunes-info-in-sidebar
title: itunes info in sidebar
url: /2004/04/01/itunes-info-in-sidebar/
wordpress_id: 490
---

because something was f[beep] up with the way [kung-tunes](http://www.kung-foo.tv/itti.php) posted the trackinfo from my itunes to the sidebar, here's the roundup on how i did it (adding to [this post](http://habi.gna.ch/blog/archives/000129.html)):

- go to mt's control panel.
- make a new blog (itunes).
- make a new category (nowplaying).
- hit "edit category attributes", toggle "accept incoming trackback pings" to yes.
- jot down the trackback url.
- add that url to kung-tunes preferences.
- make the format of kungtunes notification: 

<blockquote>&title=^t&url=http://itunes.com&#pblog_name=^p#p&#aexcerpt=^a#a</blockquote>

- add three files to the sub-blog (here: itunes), [now_playing.html](http://habi.gna.ch/blog/itunes/now_playing.html) and [lastfive.html](http://habi.gna.ch/blog/itunes/lastfive.html) and [last30.html](http://habi.gna.ch/blog/itunes/last30.html).
- for each of the three above files add something along these lines to the code: (MTAmazon optional for album cover)

<blockquote><?php
function datediff($datestr)
{
  $r = array();
  $d = time() - strtotime($datestr);
  if ($d > 86400*2)
    array_push($r, floor($d / 86400) . " days");
  elseif ($d > 86400)
    array_push($r, "1 day");
  $d = $d % 86400;
  if ($d > 7200)
    array_push($r, floor($d / 3600) . " hours");
  else if ($d > 3600)
    array_push($r, "1 hour");
  $d = $d % 3600;
  if ($d > 120)
    array_push($r, floor($d / 60) . " minutes");
  else if ($d > 60)
    array_push($r, "1 minute");
  if (!count($r))
    return "now";
  else
    return implode(" and ", $r) . " ago";
}
?>
<MTPings category="nowplaying" lastn="1"><br/>
<MTAmazon search="[MTPingBlogName] [MTPingExcerpt]" 
line="music" lastn="1">
 <a href="<MTAmazonLink>">
  <img border="0" src="<MTAmazonSmallImage>" align="left" alt="see the album" />
 </a>
</MTAmazon>
 <a href="itms://phobos.apple.com/WebObjects/MZSearch.woa/
wa/advancedSearchResults?songTerm=<$MTPingTitle encode_url="1"$>&artistTerm=<$MTPingBlogName encode_url="1"$>" title="Search at the iTunes Music Store">
<$MTPingTitle$></a><br/>

by <a href="itms://
phobos.apple.com/WebObjects/MZSearch.woa/wa/
advancedSearchResults?artistTerm=<$MTPingBlogName encode_url="1"$>" 
title="Search at the iTunes Music Store"><$MTPingBlogName$></a><br/>

from the album <a href="itms://phobos.apple.com/WebObjects/MZSearch.woa/wa/
advancedSearchResults?albumTerm=<$MTPingExcerpt encode_url="1"$>" 
title="Search at the iTunes Music Store"><$MTPingExcerpt$></a><p/>

was played <? echo datediff('<$MTPingDate format="%Y-%m-%d %H:%M:%S"$>'); ?>.

<br />
</MTPings>
<br clear="all" /></blockquote>

- thank [b.](http://bernhardseefeld.ch/) for whacking out quite a bit of the above code and helping with the initial debugging.
- prettify the code for the 5 and 30 page, because these are the pages the people are gonna look at (iterate lastn=X in: "<MTPings category="nowplaying" lastn="1"><br/>".
- add the code below to the sidebar of the main blog. 

<blockquote><?php require_once("itunes/now_playing.html"); ?>
you can also see the <a href="http://habi.gna.ch/blog/itunes/lastfive.html" target="_blank">last five</a> or the <a href="http://habi.gna.ch/blog/itunes/last30.html" target="_blank">last 30 songs</a></blockquote>

- rebuild all involved blogs.
- [wash, rinse, repeat](http://www.google.com/search?q=wash,+rinse,+repeat&ie=UTF-8&oe=UTF-8)


**btw**: you did not notice that since [i installed panther](http://habi.gna.ch/blog/archives/000233.html) kung-tunes was posting the album title as the song title, did you?

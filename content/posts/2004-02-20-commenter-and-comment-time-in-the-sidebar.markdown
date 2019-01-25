---
author: admin
comments: true
date: 2004-02-20 17:59:39+00:00
layout: post
link: http://habi.gna.ch/2004/02/20/commenter-and-comment-time-in-the-sidebar/
slug: commenter-and-comment-time-in-the-sidebar
title: commenter and comment time in the sidebar
wordpress_id: 441
categories:
- none
---

using [b.](http://www.bernhardseefeld.ch/)'s code he wrote for my [itunes-trackback-thingie](http://habi.gna.ch/blog/archives/000129.html) i prettied up the comment stuff a bit. (i hope the code he sucked out of his brain is "freeware" :-)
now you see who and when posted the last comment.
i like it, do you?

anyway, here's the full code for your abuse:


<blockquote><?php
function datediff2($datestr)
{
  $r = array();
  $d = time() - strtotime($datestr);
  if ($d > 86400*2)
    array_push($r, floor($d / 86400) . "d");
  elseif ($d > 86400)
    array_push($r, "1d");
  $d = $d % 86400;
  if ($d > 7200)
    array_push($r, floor($d / 3600) . "h");
  else if ($d > 3600)
    array_push($r, "1h");
  $d = $d % 3600;
  if ($d > 120)
    array_push($r, floor($d / 60) . "min");
  else if ($d > 60)
    array_push($r, "1min");
  if (!count($r))
    return "now";
  else
    return implode(", ", $r) . " ago";
}
?>

<div class="side">
<$MTComments lastn="5"$ sort_order="descend">
[<a href="<$MTBlogArchiveURL$><$MTCommentEntryID pad="1"$>.html"><$MTCommentAuthor$></a>, <? echo datediff2('<$MTCommentDate format="%Y-%m-%d %H:%M:%S"$>'); ?>
]<br />
</MTComments>
</div></blockquote>



i really hope berni does not mind if i post his code here.
just to make it clear: my only achievement are the last lines between <div class="side"> and </div> the rest is fully credited to the code-master b.

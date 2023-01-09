---
comments: true
date: 2004-07-21 22:25:43+00:00
link: https://habi.gna.ch/2004/07/22/programming/
slug: programming
title: programming
wordpress_id: 583
categories:
- none
---

[![suicmc_pics](https://habi.gna.ch/blog/images/suicmc_pics-tm.jpg)](https://habi.gna.ch/blog/images/suicmc_pics.jpg)coding something can be quite a long process for me.
[anja](http://www.frauraecher.ch/) mailed me some picture which i wanted to put on the homepage of the [SUICMC04](http://suicmc04.ch/).
since i wanted to do it in the simplest and cleanest possible way i thought to make little table with links to all of the pictures, so that when you click on them, they pop up in a new window with the right size, with a nifty "close window"-link.
in the end it turned out to be a longer process than i thought:

here's the way i did it:
- talk to [b.](http://bernhardseefeld.ch/) about it.
- let b. propose some php-trickery.
- code something around:


<blockquote>
<? $name = ereg_replace("[^a-zA-Z_.-]", "", $_GET['name']); ?> 
<body>
 <p align="center" class="text"><? readfile("pics/" . $name . ".txt") ?></p>
 <p align="center"><img src="pics/<? echo $name ?>.jpg"></p>
 <p align="center"><a href="javascript:window.close()" class="link">Fenster schliessen/Close Window</a></p>
</blockquote>


- add all the pics to the subdirectory /pics and add a PICNAME.txt file with the description fer each and every file.
- don't forget to use proper html-code.
- test to see if the link [../gelaende.php?name=PICNAME](http://suicmc04.ch/Gelaende/gelaende.php?name=aare) (aare for example) does work.
- be happy that [aare.jpg](http://suicmc04.ch/Gelaende/pics/aare.jpg) and [aare.txt](http://suicmc04.ch/Gelaende/pics/aare.txt) do actually get put in the code.
- make a thumbnail of each picture (iphoto comes in handy here).
- build a 4 by 4 table with all the pics.
- don't mess up the code that michel and abu made.
- insert


<blockquote><a href="../gelaende.php?name=PICNAME" onclick="window.open('http://www.suicmc04.ch/gelaende.php?name=PICNAME','popup','width=640,height=480,scrollbars=yes,resizable=yes,toolbar=no,
directories=no,location=no,menubar=no,status=yes,left=0,top=0');return false"><img src="../pics/PICNAME_t.jpg" width="56" height="56"></a></blockquote>

in each cell.
- substitute PICNAME with the actual name of the .jpg in each case (3*4*4 times) and don't forget a single one.
- thank b. for being such a nice guy.
- look at the [endresult](http://suicmc04.ch/de/plan.html).
- see that you need to look that the windows are in the right size (which they aren't, but i have to go to bed, i'll do that soon).
-go to bed.
-get up in 5 hours and 30 minutes.

---
date: 2010-03-29 20:22:29+00:00
link: https://habi.gna.ch/2010/03/29/automator-actions-zur-bildbearbeitung/
slug: automator-actions-zur-bildbearbeitung
title: Automator Actions zur Bildbearbeitung
wordpress_id: 2086
categories:
- technospeak
tags:
- automator
---

[herr chm](http://bloxxs.ch/) hat kürzlich ein schönes [panorama-bild](https://www.flickr.com/photos/macronix/4466763332/) von seinem balkon aus veroffentlicht, welches von [mir aus gesehen](https://www.flickr.com/photos/macronix/4466763332/comment72157623588015725/) ohne schwarzen rand viel besser aussehen würde.
da herr chm offenbar den [automator](http://www.macosxautomation.com/automator/) nicht kennt, habe ich hier einen kurzen screencast gemacht, wie ich dieses raffinierte feature verwende, welches von haus aus in OS X integriert ist. der screencast unten zeigt, wie einfach es ist, sich einen sogenannten service zu machen, um bilder schnell umzuwandeln:

<object id="scPlayer" type="application/futuresplash" width="720" height="450"><param name="movie" value="http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/jingswfplayer.swf"><param name="quality" value="high"><param name="bgcolor" value="#FFFFFF"><param name="flashVars" value="thumb=http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/FirstFrame.jpg&amp;containerwidth=720&amp;containerheight=450&amp;content=http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/00000002.swf"><param name="allowFullScreen" value="true"><param name="scale" value="showall"><param name="allowScriptAccess" value="always"><param name="base" value="http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/"><embed src="http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/jingswfplayer.swf" quality="high" bgcolor="#FFFFFF" type="application/futuresplash" allowscriptaccess="always" flashvars="thumb=http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/FirstFrame.jpg&amp;containerwidth=720&amp;containerheight=450&amp;content=http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/00000002.swf" allowfullscreen="true" base="http://content.screencast.com/users/haberthuer/folders/Jing/media/d743a203-72e8-4333-bf92-bb591f7df6d9/" scale="showall" width="720" height="450"></object>

da es sicher ein paar eilige gibt, die sich das nicht im automator nachbauen wollen, habe ich meine kleinen scripte hier hochgeladen.
diese skripte mussen in `~/Library/Services/` kopiert werden, das heisst in den library-ordner in eurem home-verzeichnis, und sind dann mit einem rechtsklick auf bilder im finder zu sehen (wie im screencast oben gezeigt).

Achtung: Ich habe die services so gemacht, dass KEINE kopie der bilder erstellt/behalten wird, sondern das bild geändert wird.
wem das nicht passt, bearbeitet die heruntergeladenen services vor dem kopieren in `~Library/Services/` mit seinem eigenen automator!
die benutzung der hier zur verfugung gestellten skripte erfolgt somit auf eigene gefahr!
bei falscher benutzung geht die [7 TeV-Kollision vom LHC](http://press.web.cern.ch/press/PressReleases/Releases2010/PR06.10E.html) morgen früh schief und wir landen alle in einem schwarzen loch!!1!

die skripte sind im file [automatorworkflows.zip](https://habi.gna.ch/wp-content/uploads/automatorworkflows.zip) zu finden.
dieses file enthält

* `convert>jpg`: konvertiert das gewählte bild (oder die gewählten 100 bilder) von irgendeinem erkannten format nach .jpg
* `convert>png`: macht dasselbe nach [png](https://en.wikipedia.org/wiki/Portable_Network_Graphics)
* `resize>1024`: ändert die grösse der längsten seite des bildes auf 1024 pixel
* `resize>2048`: dasselbe in grün, bzw. auf 2048 pixel
* `resize>ask`: ändert die grösse auf eine pixel-anzahl, welche beim start des skriptes eingegeben werden muss
* `rotate>left`: rotiert das bild (oder die 2347 bilder) einmal nach links
* `rotate>right`: dasselbe nach rechts

viel spass damit, herr chm (oder wer auch immer die kleinen skripte brauchen will)

btw: für grössere bildbearbeitungs-sachen (z.B. knapp [12000 Bilder beschneiden](http://identi.ca/notice/18168031), die grösse zu ändern oder in ein anderes format zu konvertieren) ist immernoch [ImageMagick](http://www.imagemagick.org/) unschlagbar.
dies bedingt aber immer einen umweg übers terminal und eine installation von [macports](http://www.macports.org/) und weiteren abhängigkeiten, automator ist im betriebssystem dabei.

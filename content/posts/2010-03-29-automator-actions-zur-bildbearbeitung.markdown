---
author: admin
comments: true
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

[herr chm](http://bloxxs.ch/) hat kurzlich ein schönes [panorama-bild](http://www.flickr.com/photos/macronix/4466763332/) von seinem balkon aus veroffentlicht, welches von [mir aus gesehen](http://www.flickr.com/photos/macronix/4466763332/comment72157623588015725/) ohne schwarzen rand viel besser aussehen wurde. da herr chm offenbar den [automator](http://www.macosxautomation.com/automator/) nicht kennt, habe ich hier einen kurzen screencast gemacht, wie ich dieses raffinierte feature verwende, welches von haus aus in OS X integriert ist. der screencast unten zeigt, wie einfach es ist, sich einen sogenannten service zu machen, um bilder schnell umzuwandeln:


  
  
  
  
  
  
  
  
  



da es sicher ein paar eilige gibt, die sich das nicht im automator nachbauen wollen, habe ich meine kleinen scripte hier hochgeladen. diese skripte mussen in ~/Library/Services/ kopiert werden, das heisst in den library-ordner in eurem home-verzeichnis, und sind dann mit einem rechtsklick auf bilder im finder zu sehen (wie im screencast oben gezeigt).




Achtung: Ich habe die services so gemacht, dass KEINE kopie der bilder erstellt/behalten wird, sondern das bild geandert wird. wem das nicht passt, bearbeitet die heruntergeladenen services vor dem kopieren in ~library/services/ mit seinem eigenen automator! die benutzung der hier zur verfugung gestellten skripte erfolgt somit auf eigene gefahr! bei falscher benutzung geht die [7 TeV-Kollision vom LHC](http://press.web.cern.ch/press/PressReleases/Releases2010/PR06.10E.html) morgen fruh schief und wir landen alle in einem schwarzen loch!!1!




die skripte sind im file [automatorworkflows.zip](https://habi.gna.ch/wp-content/uploads/automatorworkflows.zip) zu finden. dieses file enthalt  






  
  * convert>jpg: konvertiert das gewahlte bild (oder die gewahlten 100 bilder) von irgendeinem erkannten format nach .jpg  



  
  * convert>png: macht dasselbe nach [png](https://en.wikipedia.org/wiki/Portable_Network_Graphics)


  
  * resize>1024: andert die grosse der langsten seite des bildes auf 1024 pixel


  
  * resize>2048: dasselbe in grun, bzw. auf die grosse 2048 pixel


  
  * resize>ask: andert die grosse auf eine pixel-anzahl, welche beim start des skriptes eingegeben werden muss


  
  * rotate>left: rotiert das bild (oder die 2347 bilder) einmal nach links


  
  * rotate>right: dasselbe nach rechts




viel spass damit, herr chm (oder wer auch immer die kleinen skripte brauchen will)




btw: für grossere bildbearbeitungs-sachen (z.B. knapp [12000 Bilder beschneiden](http://identi.ca/notice/18168031), die grosse zu andern oder in ein anderes format zu konvertieren) ist immernoch [ImageMagick](http://www.imagemagick.org/) unschlagbar. dies bedingt aber immer einen umweg übers terminal und eine installation von [macports](http://www.macports.org/) und weiteren abhangigkeiten, automator ist im betriebssystem dabei.  





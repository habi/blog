---
author: admin
categories:
- switzerland
- technospeak
- tschörman
comments: true
date: 2010-09-24T10:25:34Z
link: http://habi.gna.ch/2010/09/24/zrich-im-zeitraffer/
slug: zrich-im-zeitraffer
tags:
- timelapse
title: Zürich im Zeitraffer
url: /2010/09/24/zrich-im-zeitraffer/
wordpress_id: 2215
---

Letzthin ist mir aufgefallen, dass die Bilder der [SWITCH](http://switch.ch/)-[Webcam](http://cam.switch.ch/about.en.html), die seit 2008 schon sauberlich in einem [Archiv](http://cam.switch.ch/cgi-bin/pano2.pl) auf denen ihrem Webserver abgespeichert werden. Da die SWITCH-Cam jede Stunde ein Panoramabild der Innenstadtregion, der ETH und dem unteren Seebecken macht, habe ich mir gedacht, dass so schone Zeitrafferaufnahmen entstehen konnten.




Da ich die schnelle Datenleitung der SWITCH ausnutzen wollte, habe ich mir (in der Freizeit, ja) im Buro ein kleines [MATLAB](http://de.wikipedia.org/wiki/Matlab)-Skript [1] geschrieben, welches fur jede Stunde seit 2008 das Panoramabild von Zurich heruntergeladen hat. Fur Interessierte ist das Skript unten dargestellt und kann [hier](http://habi.pastebin.com/gYCjzhFx) heruntergeladen und angeschaut werden.







In den ersten paar Zeilen werden die verschiedenen Tage der Monate eingestellt, dann wird fur jede Stunde jedes Tages seit 2008 das Webcambild runtergeladen und in einem Verzeichnis gespeichert. Zeitweise kommt es vor, dass ein Bild nicht gefunden wurde, deshalb ist ab Zeile 44 eine Sicherheitsschlaufe eingebaut, die das Skript nicht abbricht. Damit's dann schon zeitrafferig aussieht habe ich mich eines kleinen [ImageMagick](http://www.imagemagick.org/)-Tricks bedient, und die Bilder noch mit dem Datum und der Uhrzeit beschriftet (Zeile 51-60). Schlussendlich sind fur jede Stunde seit Januar 2008 bis September 2010 knapp 1000 Bilder geschrieben worden, die ich dann mit Quicktime Pro zu einem Zeitraffer-Film zusammengesetzt habe.




Das heisst, schlussendlich habe ich fur jede Stunde von Mitternacht bis 23.00 Uhr einen Zeitrafferfilm der Stadt Zurich. Alle diese hier zu zeigen wurde den Rahmen dieses Blogeintrags sprengen, deshalb hier nur ein paar davon. Alle 24 Filme sind in diesem [Album auf Vimeo](http://vimeo.com/album/1179251) zu finden. Die Filme haben bei der Flash-Konvertierung ziemlich gelitten, wer die Zeitraffers in HD-Qualitat herunterladen will, soll auf die jeweilige Video-Seite gehen. Unten rechts kann das Original heruntergeladen werden, die Videos stehen unter einer CC-Lizenz zur Verfugung. Hoffentlich passt das auch den Herren und Damen der SWITCH :)




Zurich um Mitternacht







Zurich um Neun Uhr Morgens




  





Zurich um Funf Uhr Abends




  





Zurich um Neun Uhr Abends




[1]: Ja, es ginge auch anders, gerne z.B. mit Python. MATLAB kenne ich aber gut und brauche es viel. Deshalb.  


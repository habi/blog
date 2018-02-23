---
author: admin
categories:
- movies
- personal
- technospeak
- work
comments: true
date: 2013-09-15T14:12:08Z
link: http://habi.gna.ch/2013/09/15/mein-bisher-langstes-zeitrafferfilmi/
slug: mein-bisher-langstes-zeitrafferfilmi
tags:
- movies
title: Mein bisher längstes Zeitrafferfilmi
wordpress_id: 3199
---

Der Film selber ist gar nicht so lang, aber die Herstellung dauerte lange.




Wie aufmerksame MitleserInnen wissen, versuche ich während den Arbeitszeiten [1] Wissenschaft zu betreiben. Das hat zur Folge, dass die erzielten Resultate der Öffentlichkeit zugänglich gemacht werden sollten, nachdem die Auswertung erfolgreich gelungen ist.




Mit den Tomografie-Daten, die unter anderem während meiner Doktorarbeit entstanden, sollen neue Erkenntnisse über das nachgeburtliche Wachstum der Lunge erzielt werden. Die Methode, wie wir einzelne funktionale Einheiten der Lunge, die sogenannten Acini aus den Datensätzen extrahiert haben und diese anschliessend nach allen Regeln der Kunst analysiert haben, beschreiben wir in der Publikation "[Visualization and stereological characterization of individual rat lung acini by high-resolution X-ray tomographic microscopy](http://dx.doi.org/10.1152/japplphysiol.00642.2013)", die kürzlich im [Journal of Applied Pyhsiology](http://jap.physiology.org) erschienen ist.




Jedes von mir erstellte Dokument welches ein Bild enthält und länger als eine Seite ist, schreibe ich in [LaTeX](http://www.latex-project.org) [2], das macht es möglich, dass ich mit [Subversion](http://subversion.tigris.org) [3] eine sogenannte Versionenkontrolle mache, d.h. ich halte immer mal wieder den gegenwärtigen Zustand des Textes fest, bevor ich daran weiterarbeite. Später kann dann, falls nötig, auf eine alte Version zurückgegriffen werden, oder nachvollzogen werden, wer was wann geschrieben hat.




Vor fast einem Jahr las ich auf [FlowingData](http://flowingdata.com/2012/11/30/time-lapse-writing-of-a-research-paper/), wie ein Wissenschaftler den Verlauf seiner Publikation in einem Zeitraffer-Film zeigt, das dachte ich, das kann ich auch, ich hab' ja jede Version auf dem Code-Server der Uni Bern [4] gespeichert.




Mit einem [Python-Skript](https://github.com/habi/python/blob/master/acinuspaper-timelapse.py) habe ich jede einzelne Version aus dem Subversion-Archiv in ein einzelnes Unterverzeichnis geladen. Mit einem [zweiten Skript](https://github.com/habi/python/blob/master/acinuspaper-timelapse-compiler.py) habe ich aus jeder Version ein PDF gemacht, und alle Seiten dieses PDFs als Bild gespeichert. Mit etwas Nachbearbeitung in iMovie ist dann unten eingebundenes Zeitraffer-Filmli entstanden: Die lange Arbeit an einem Paper visualisiert in 45 Sekunden.




Damit mensch überhaupt etwas sieht, habe ich den Film mal in voller Grösse zu [youtube hochgeladen](http://www.youtube.com/watch?v=HhFC680lQDU) und in halber Grösse hier eingebunden.




[1]: Und manchmal ausserhalb der normalen Arbeitszeiten  

[2]: Oder in [Markdown](http://daringfireball.net/projects/markdown/) mit Umweg über [pandoc](http://johnmacfarlane.net/pandoc/) zum Zielformat  

[3]: Oder neuerdings ausschliesslich [git  
](http://git-scm.com)[4]: Besser gesagt, ein Subversion-Server auf der virtuellen Serverfarm der Uni Bern den schlussendlich nur ich gebraucht habe...

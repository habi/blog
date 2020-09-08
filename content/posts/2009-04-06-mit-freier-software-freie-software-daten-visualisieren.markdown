---
author: admin
comments: true
date: 2009-04-06 22:24:48+00:00
link: https://habi.gna.ch/2009/04/06/mit-freier-software-freie-software-daten-visualisieren/
slug: mit-freier-software-freie-software-daten-visualisieren
title: mit freier software freie software-daten visualisieren [update]
wordpress_id: 1702
categories:
- gadgets and gizmos
- technospeak
tags:
- identi.ca
- latex
- microblog
- pgf
- python
---

seit einen [halben jahr](http://identi.ca/notice/685038) beantworte ich die frage "what's up?" nicht bei twitter, sondern der [quell-offenen](http://laconi.ca/trac/) alternative, bei [identi.ca](http://identi.ca/) [1]. über die beweggründe, eine offene alternative zum fail whale zu benutzen soll hier nicht die rede sein [2].




in den letzten tagen hab' ich mich gefragt, wie schnell identi.ca wächst. jedes status-update wird bei identi.ca als wachsende nummer, in der form http://identi.ca/notice/1 [3]. jede dieser nachrichten wird dann mit einer klar definierten zeit auf der webseite festgehalten. aufgrund der beiden parameter nummer und zeit könnte schon ein kleiner graph entstehen.




da es mir aber äusserst mühsam erschien, genug status updates anzusurfen, die jeweiligen zeiten aufzuschreiben, dies in eine excel-tabelle [4] einzutragen und dann einen plot zu generieren, habe ich mich nach kurzer überlegung entschieden, das [ganze anders anzugehen](http://identi.ca/notice/3202500): mit einem kleinen python-skript (siehe [hier](http://habi.pastebin.com/f7f1dbbcf)) lade ich eine definierte nummer von sogenannten dents, mache eine kleine aufhübschung mit ein bisschen text-ersetzung und schreibe das ganze in ein komma-separiertes textfile.




in diesem textfile landen alle parameter, die für einen plot notwendig sind. nach weitere kleinerer rumbastelei landet das ganze in 23 zeilen [LaTeX](http://www.latex-project.org/)-code (siehe [hier](http://habi.pastebin.com/f4edf34d)), mit dem dann mit der hilfe von [tikz](http://sourceforge.net/projects/pgf/) und [pgfplots](http://pgfplots.sourceforge.net/) untenstehende graphik entsteht [5]. die rumbastelei hat vor allem mit der anpassung von zeitspannen zu tun, damit's ein schöner plot wird.





  [![dents.png](https://habi.gna.ch/wp-content/uploads/2009/04/dents.png)](https://habi.gna.ch/wp-content/uploads/2009/04/dents.png)[  
](https://habi.gna.ch/wp-content/uploads/2009/04/dents.png)





im ganzen plot sind nur 55 datenpunkte verwurstet, aber nichtsdestotrotz kann mann einen eher exponentiellen anstieg der anzahl nachrichten in den ersten 300 tage identi.ca feststellen. damit der plot aussagekräftiger wird, muss ich mein python-skript mal etwas länger laufen lassen, oder jemand interessiert sich wirklich so fest dafür, dass er es mit meiner vorlage weiterführt oder verbessert.

dieser post soll auch dazu dienen, dass ich - nach dem [blgmndybrn special im musigbistrot](http://blgmndybrn.ch/?p=39) - grad noch [bastian](http://blog.dasrecht.net/) einen richtigen hinweis auf identi.ca und LaTex geben kann: bastian, identi.ca ist oben abgehandelt, meine code-schnipsel zu LaTeX landen [hier](http://www.ana.unibe.ch/~haberthuer/latex), diejenigen zur bildverarbeitung mit imagemagick [hier](http://www.ana.unibe.ch/~haberthuer/imageprocessing/imagemagick). weiter wollte [this](http://www.borniert.com/) noch auf das schöne paket hingewiesen werden, mit dem mann - mit 23 zeilen code - solche plots wie oben stehend generieren kann. eben, [pgfplots](http://pgfplots.sourceforge.net/) und mein beispiel an [LaTeX-code](http://habi.pastebin.com/f4edf34d).  

also, wenn ich für die ausrechnung der tage seit dem start nicht doch gestern abend numbers verwendet hätte, würde auch der titel dieses eintrages stimmen, mit python habe ich die frei verfügbaren daten von identi.ca geladen, in ein text-file geschrieben und mit dem übermächtigen LaTeX daraus ein kleines, aber feines pdf erstellt.  

und ja, ich geb's zu, ich bin ein nerd!  



[1]: seit längerer zeit wird auch mein status beim moloch facebook von identi.ca aus aktualisiert




[2]: "my data", "my content", portabilität, freie meinungsäusserung, etc.




[3]: hier das erste status-update von [evan](http://evan.prodromou.name/), dem kopf hinter dem ganzen




[4]: oder [numbers](http://www.apple.com/iwork/numbers/)




[5]: natürlich als pdf, hier der einfachheit halber als .png-bild




ps: fast noch schöner sieht's mit logarithmischer y-achse aus; dieser plot wurde mit der leicht modifizierten version des latex-codes ([hier zu finden](http://habi.pastebin.com/f11baf1e3)) erstellt.




![logdents.png](https://habi.gna.ch/wp-content/uploads/2009/04/logdents.png)



**update:** [tobias diekershoff](http://tobias.diekershoff.homeunix.net/) hat heute ein viel schöneres skript und eine viel fundiertere aussage über die anzahl dents veröffentlicht. falls es jemand interessiert: [hier weiterlesen](http://tobias.diekershoff.homeunix.net/pivot/entry.php?id=75 )!

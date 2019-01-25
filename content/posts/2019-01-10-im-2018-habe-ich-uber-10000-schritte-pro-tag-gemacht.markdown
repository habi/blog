---
author: admin
comments: true
date: 2019-01-10 21:19:25+00:00
layout: post
link: http://habi.gna.ch/2019/01/10/im-2018-habe-ich-uber-10000-schritte-pro-tag-gemacht/
slug: im-2018-habe-ich-uber-10000-schritte-pro-tag-gemacht
title: Im 2018 habe ich über 10000 Schritte pro Tag gemacht
wordpress_id: 5522
categories:
- personal
tags:
- code
- jahresrückblick
- jahresrückblick18
- jupyter
- python
- stepcount
---

Hier der nächste meiner Posts zum 2018. Eine kleine Analyse meiner täglichen Schritte. Dieser und andere Posts sind unter dem Tag `[jahresrückblick18](http://habi.gna.ch/tag/jahresruckblick18)` zu finden.

Seit September 2014 weiss ich ungefähr, wieviele Schritte ich jeden Tag mache. Die Schritte werden mit einem Garmin [vívofit](https://buy.garmin.com/en-US/US/p/143405) (bis ca. Mai 2016) und einer Garmin [Forerunner 235](https://buy.garmin.com/en-US/US/p/529988) (seit ca. dann) aufgezeichnet.  
Die Export-Funktion von Garmin liefert leider keine nach Tag aufgeschlüsselten Daten. Da die Schrittzahlen aber via [Garmin Connect](https://connect.garmin.com/) auf meinem Telefon in [Apple Health](https://www.apple.com/ios/health/) landen, konnte ich mit [QS Access](http://quantifiedself.com/qs-access-app/) einfach eine [CSV](ttps://en.wikipedia.org/wiki/Comma-separated_values)-Datei erstellen, die mit etwas Python-Code analysiert wird.

Mit etwas Python-Code (siehe ganz unten) habe ich die CSV-Datei eingelesen und kurz "analysiert": In der Summe habe ich im 2018 3.85 Millionen Schritte gemacht, das sind 10558 Schritte pro Tag. Am meisten Schritte gab's am Instituts-Ausflug ([siehe August hier](http://habi.gna.ch/2019/01/08/2018-in-bildern/)), nämlich 21465 Schritte. Am wenigsten gab's am 5. Juli mit 303 Schritten, da ist mir die Uhr abgestürzt (ein Satz, den man sich früher so auch nicht erträumt hätte). Am zweitwenigsten gab's an einem langweiligen Ferientag am Meer mit 3072 Schritten.

Aufgeschlüsselt nach Tagen sieht das so aus. Die geneigte Leserschaft erkennt so, wann ich Papa-Tag habe und wann ich Mittags äusserst selten joggen gehe (Donnerstag, bzw. Dienstag).

![](http://habi.gna.ch/wp-content/uploads/2019/01/output_17_0.png)

Aufgeschlüsselt nach Monaten sieht das so aus. Man erkennt ziemlich schön, wann ich meinen zweimonatigen unbezahlten Vaterschafts-Urlaubd hatte und wann die langen Ferien waren :)![](http://habi.gna.ch/wp-content/uploads/2019/01/output_18_0.png)



Wer sich für den kompletten Code interessiert, findet das Jupyter Notebook [hier auf GitHub](https://github.com/habi/steps), oder[ klickt hier für eine lauffähige Version des Notebooks auf  Binder.](https://mybinder.org/v2/gh/habi/steps/master)

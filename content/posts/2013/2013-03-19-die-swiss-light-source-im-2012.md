---
comments: true
date: 2013-03-19 21:50:08+00:00
link: https://habi.gna.ch/2013/03/19/die-swiss-light-source-im-2012/
slug: die-swiss-light-source-im-2012
title: Die Swiss Light Source im 2012
wordpress_id: 3069
categories:
- movies
- personal
- technospeak
tags:
- hugin
- movies
- panorama
- sls
- swiss light source
- video
---

Wer meinen flickr-Stream etwas im Auge behält, weiss, dass ich im 2012 jeden Monat ein Panorama im Innenhof der [Swiss Light Source](http://www.psi.ch/sls/) gemacht habe.
Die Panoramas zeigen die Rundum-Sicht im imposanten Innenhof, teilweise bei schönem Wetter, teilweise bei weniger schönem.

Damit ich mit den Bildern etwas dynamischer den Jahresverlauf zeigen kann, habe ich mir ein kleines Python-Skript geschrieben [1], welches die 12 [stereographischen Panoramen](https://en.wikipedia.org/wiki/Stereographic_projection) nimmt, ineinander überblendet und die ganze Sache nadisna um 360° rotiert.
Das Skript ist unten eingebunden und kann in meinem [Python-GitHub-Repository](https://github.com/habi/python) geforkt und kopiert werden, wenn Bedarf daran besteht.
Ich habe versucht, das Skript grosszügig zu kommentieren, so dass die interessierte Leserschaft sieht, was wie gemacht wird :)

<script src="http://gist-it.appspot.com/github/habi/python/blob/master/blendit.py?slice=11:"></script>

Mit der Hilfe der [AppStore-Neuentdeckung Zeitraffer](https://itun.es/ch/KabiI.m) habe ich die jeweils 100 Bilder jeder Monats-Überblendung zu einem Film zusammengesetzt und mit iMovie noch etwas Titelei dazugemacht.
Das Endprodukt dieses ganzen Vorgangs ist der unten eingebundene Film: das Jahr 2012 im Innenhof der SLS in einer Minute.

{{< vimeo 62185694 >}}

[1]: In den letzten Monaten programmierte ich etwas häufiger als auch schon, dabei habe ich die Einfachheit von Git kennengelernt. Mittlerweilen habe ich einen grossen Teil meines (öffentlichen) Programm- und Skript-Codes [bei Github](https://github.com/habi) deponiert.

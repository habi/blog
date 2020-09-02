---
author: admin
comments: true
date: 2010-11-19 09:20:43+00:00
link: http://habi.gna.ch/2010/11/19/surfen-ohne-flashplayer-funktioniert-auf-os-x-wunderbar/
slug: surfen-ohne-flashplayer-funktioniert-auf-os-x-wunderbar
title: Surfen ohne Flashplayer funktioniert auf OS X wunderbar
wordpress_id: 2294
categories:
- technospeak
tags:
- flash
- html5
- vimeo
- youtube
---

Seit der Neuvorstellung des MacBook Airs vor ein paar Wochen ist mir aufgefallen, dass die neuen Laptops von Apple zwar mit [Flash](http://en.wikipedia.org/wiki/Flash_memory), aber ohne [Flash](http://en.wikipedia.org/wiki/Adobe_Flash) ausgeliefert werden. In den Hintergrundberichten dazu war zu lesen, dass dies unter anderem wohl aus softwarepolitischen Überlegungen gemacht wurde, wichtiger ist aber, dass die Laptops dadurch im Surf-Betrieb stabiler und stromsparender laufen, da der Flash Player prozessorintensiv und nicht ganz fehlerfrei programmiert ist. Schon seit sehr langer Zeit surfte ich mit [ClickToFlash](http://clicktoflash.com/) durch die Weiten des Internetzes, um dem Problem entgegenzuwirken. Dieses Plugin verhinderte aber nicht, dass der Flash Player im Hintergrund trotzdem geladen wird und Speicher sowie Prozessorzeit verbraucht.

Vor ein paar Tagen habe ich bei [Herr Gruber](http://daringfireball.net/2010/11/flash_free_and_cheating_with_google_chrome) drüben gelesen, wie einfach die Entfernung des [Adobe Flash Players](http://www.adobe.com/products/flashplayer/) unter Mac OS X ist. Eine solche Entfernung (oder genauer Deaktivierung) ist nicht nur einfach, sondern - wie mein Praxistest in den letzten [10 Tagen zeigt](http://identi.ca/notice/58271706) - dank neuen Netztechnologien erstaunlich schmerzlos.

Seit 10 Tagen surfe ich fast ausschliesslich Flash Player-frei durch das Internet. Gemacht habe ich das nach [Herr Grubers Anleitung](http://daringfireball.net/2010/11/flash_free_and_cheating_with_google_chrome) so:
  
  * Im Ordner /Library/ einen neuen Ordner "Internet Plugins (disabled)" erstellen und aus dem Ordner "Internet Plugins" die Dateien Flash Player.plugin, flashplayer.xpt und NP-PPC-Dir-Shockwave ruberverschieben. Dies deaktiviert den Flash Player. Aus- und wieder einloggen oder neu starten aktiviert diese Einstellungen.

  * [Youtube auf HTML5 umstellen](http://youtube.com/html5), das aktiviert den HTML5-Player auf YouTube
  * [Vimeo auf HTML5 umstellen](http://vimeo.com/blog:268)
  * Die Safari-Extension [Youtube5](http://www.verticalforest.com/youtube5-extension/) installieren, damit auch eingebundene YouTube-Videos ohne Flash Player angezeigt werden.

So bewege ich mich nun seit 10 Tagen durchs Netz und habe nur ein paar Einschrankungen bemerkt. Entweder weil ich (noch) keinen Vimeo Pro Account habe oder weil die Youtube5-Extension nicht korrekt funktioniert werden die eingebetteten Videos von mir nicht als HTML5 ausgeliefert. Teilweise werden Videos von anderen Seiten als Youtube und Vimeo nicht als HTML5-Alternative ausgeliefert (z.B. [Spiegel.de](http://spiegel.de/video/video-1086540.html) oder [NewsNetz](http://spiegel.de/video/video-1086540.html)). Flashgames (z.B. die witzigen der [Nothing Agency](https://nothing.ch/works/games)) funktionieren nicht und die [Flickr-Diashows werden auch nicht angezeigt](http://cl.ly/3Iy6). Diese Probleme sind aber sehr einfach losbar. Und wie ich im [vorhergehenden Eintrag](http://habi.gna.ch/2010/11/19/ausschaffungsinitiative-im-praxistest/) geschrieben habe, ist ohne Flash Player der Link zum Einbinden von issuu.com-Dokumenten zwar kurz sichtbar, fuhr aber nach einem Klick und der Anzeige des [Einbett-Codes](http://issuu.com/surprise/docs/surprise_237?showEmbed=true) direkt zum Dokument.

Fur solche Spezialfalle greife ich auf [Google Chrome](http://www.google.com/chrome/) zuruck. Google Chrome hat seinen eigenen Flash Player eingebaut, der nach dem Beenden des Browsers auch sauber wieder aus dem Speicher geloscht wird und so nach dem Anschauen eines Videos oder einer Diashow keine weiteren Probleme macht.

Fazit: Der Flash Player ist dank neuen Netztechnologien heute nicht mehr zwingend notwendig. [HTML5](http://slides.html5rocks.com/) [FTW](http://www.urbandictionary.com/define.php?term=ftw)!

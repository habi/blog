---
author: admin
categories:
- technospeak
comments: true
date: 2017-08-22T20:31:14Z
link: http://habi.gna.ch/2017/08/22/1000e-bilder-fur-osm-bereitstellen-mapillary-mit-gopro-hero-4-session/
slug: 1000e-bilder-fur-osm-bereitstellen-mapillary-mit-gopro-hero-4-session
tags:
- geodata
- geoinformation
- mapillary
- openstreetmap
title: 1000e Bilder für OSM bereitstellen | Mapillary mit GoPro Hero 4 Session
wordpress_id: 5168
---

Vor [einiger Zeit](http://habi.gna.ch/2017/03/29/osm-mapillary/) hab ich ja schon mal darüber geschrieben, wie mensch die <del>Welt</del> [kostenloses Kartenmaterial](http://osm.org) verbessern kann.

Da das Zusammenspiel der Mapillary-App mit der GoPro Hero 4 Session [nicht ganz problemfrei ist](https://github.com/mapillary/mapillary_issues/issues?utf8=?&q=is%3Aissue%20hero%20session%20) habe ich letzthin beim Velopendeln 'was neues versucht.

Wir waren ja [eine Woche mehr oder weniger in den Ferien am Thunersee](https://www.flickr.com/photos/habi/albums/72157684559049111), ich bin dann doch zweimal von dort aus arbeiten gegangen, einmal mit A. im Zug (sie ging in die Kita), [einmal mit dem Velo](https://www.strava.com/activities/1116601685).
Mit der Zeitraffer-Funktion der Kamera habe ich eine gute Stunde Fotos vom Lenker aus gemacht, dazu mit der [Aktivitäts-Uhr](https://buy.garmin.com/en-US/US/p/523893) die Positionen aufgenommen.

Da der korrekte Transfer der gut 2000 Bilder zu [Mapillary](https://www.mapillary.com) doch nicht ganz einfach war, beschreibe ich hier den Ablauf, auch damit ich das das nächste Mal nachschauen kann [1].

Als erstes muss mensch das [Garmin TPX](https://duckduckgo.com/?q=garmin+tpx&t=osx&ia=web)-File in ein normales GPX-File umwandeln (Das File landet übrigens dank [Tapiriik](https://tapiriik.com) automatisch auf meinem Computer).
Dank GPSBabel und untenstehendem Kommando geht das ganz easy.

[code lang=bash]
gpsbabel -i gtrnctr -f ~/Dropbox/Apps/tapiriik/2017/08017.08.04.Vom\ Ländli\ us\ ga\ schaffe_Cycling.tcx -o gpx -F ~/Desktop/thunbern.gpx
[/code]

Jetzt müssen wir die Fotos vorbereiten, d.h. korrekt geotaggen und für Mapillary vorbereiten.

[code lang=bash]
cd ~/Dev
git clone git@github.com:mapillary/mapillary_tools.git
[/code]

lädt die [Mapillary Tools](https://github.com/mapillary/mapillary_tools) auf den Kompi. Theoretisch würde das [geotag_from_gpx.py](https://github.com/mapillary/mapillary_tools/blob/master/python/geotag_from_gpx.py)-Skript das geotaggen erledigen. Das Skript hat aber einen Fehler, also muss mensch diesen [erst korrigieren](https://github.com/mapillary/mapillary_tools/pull/179).

Dann klappt das Geotagging wunderbar mit

[code lang=bash]
python ~/Dev/mapillary_tools/python/geotag_from_gpx.py ~/Pictures/GoPro/2017-08-04/HERO4 Session 1/Time Lapse 3/ ~/Desktop/thunbern.gpx
[/code]

Zum hochladen der Bilder müssen zuerst sogenannte [Umgebungs-Variabeln](https://stackoverflow.com/questions/135688/setting-environment-variables-in-os-x) gesetzt werden. Die genauen Werte für deinen User-Account sind in deinen [Mapillary settings](https://www.mapillary.com/app/settings/developers) zu finden und landen in deinem `~/.bashrc`.

[code lang=bash]
export MAPILLARY_USERNAME="habi"
MAPILLARY_PERMISSION_HASH="GanzVieleBuchstaben"
export MAPILLARY_SIGNATURE_HASH="NochmalVieleBuchstaben"
[/code]

Dann geht das hochladen der Bilder flink und automatisch mit

[code lang=bash]
python ~/Dev/mapillary_tools/python/upload_with_authentication.py ~/Pictures/GoPro/2017-08-04/HERO4\ Session\ 1/Time\ Lapse\ 
3/
[/code]

(Wenigstens theoretisch, ich musste die Vorgänge geotagging und hochladen ein paar Mal wiederholen, bis alle Bilder hochgeladen waren.)

Das Ganze sieht dann in etwa so aus.



Und die Fotos ermöglichen es dann dem geneigten OSM-Nutzer oder der OSM-Nutzerin, anhand der Fotos die OpenStreetMap zu verbessern, sei das z.B. um einen [neuen Kreisel einzuzeichnen](http://www.openstreetmap.org/changeset/50963529#map=19/46.90454/7.53661) oder [generell ein paar Verbesserungen zu machen](http://blog.mapillary.com/tutorials/2017/08/03/adding-building-attributes-to-openstreetmap.html).

[1]: Oder mit den insgesamt [knapp 3000 Photos](https://www.mapillary.com/map/im/1mFs6nQPwiZPK-lZ7_si0A) von der [Hallo Velo](https://hallovelo.be)-Runde wiederholen konnte.

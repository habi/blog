---
title: "Die Bahnhofstrassen in jeder Schweizer Sprachregion"
date: 2023-11-114T20:50:00+02:00
slug: die-bahnhofstrassen-in-jeder-schweizer-sprachregion v
categories:
- code
tags:
- openstreetmap
- nerdism
- datenjonglage
---

Letzhin hatte ich es bei einem Fiirabe-'Getränk der Wahl' von Bahnhofstrassen, wir diskutierten, ob's ächt fast in jeder Gemeinde eine solche gibt.
Und welches ächt die längste Bahnhofstrasse der Schweiz ist.
Solche lustigen Fragen völlig over-engineered zu klären ist ja etwas, das ich gerne mache, drum das untenstehende.

[Amanda Mc Cann](https://www.openstreetmap.org/user/amapanda%20᚛ᚐᚋᚐᚅᚇᚐ᚜%20🏳%EF%B8%8F%E2%80%8D🌈) hat ein Tool entwickelt, mit dem sogenante [`way`](https://wiki.openstreetmap.org/wiki/DE:Way)s in OpenStreetMap zusammenzufassen und zu analysieren.
Im OpenStreetMap Datenmodell werden Strassen[^1]  manchmal in einzelne Segmente aufgeteilt, wenn Eigenschaften daran unterschiedlich sind, wie beispielsweise [die Marktgasse](https://www.openstreetmap.org/way/386805095) in Bern, die als [11 einzelne `way`s](https://osm.li/EpV) erfasst ist.

Amandas Tool [`osm-lump-ways`](https://github.com/amandasaurus/osm-lump-ways) fasst die aus datentechnisch getrennten Dinge wieder zusammen, und macht es möglich, damit etwas Datenjonglage zu betreiben.
Mit dem Tool ist es z.B. möglich, nach zusammenhängenden 'Bahnhofstrassen' zu suchen und diese der Länge nach zu sortieren.
Damit lässt sich die Eingangs gestellte Frage nach der längsten Bahnhofstrasse der Schweiz ziemlich einfach beantworten.

Das Tool installiert sich flink so (sofern vorher auch `brew install rust` gemacht wurde).

````bash
cd ~Dev
git clone git@github.com:amandasaurus/osm-lump-ways.git
cd osm-lump-ways
cargo install osm-lump-ways
````

Die Geofabrik bietet einen Service an, mit dem OpenStreetMap-Daten einfach runtergeladen werden können, sogenannte '[Extracts](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)`, die etwas einfacher im Handling sind, als die 132 GB an kompletten, komprimierten Daten.

Ein einfacher Befehl wie unten und schwupps sind die 424 MB OpenStreetMap-Daten nur aus der Schweiz auf der Festplatte. 
````bash
wget https://download.geofabrik.de/europe/switzerland-latest.osm.pbf
````

Nachdem mit `./osm-lump-ways -h` kurz die Hilfe des Tools durchgeschaut wurde ist es einfach, die längste Bahnhofstrasse der Schweiz rauszuklauben, nämlich mit `./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f name~"[b|B]ahnhof" -o ch-bahnhof.geojson --only-longest-n-per-file 1`.
Der Aufruf sucht im neuesten Export aus der Schweiz nach allen `highway`-Tags, führt diejenigen mit dem Namen Bahnhofstrasse zusammen und schreibt die längsten zusammenhängenden davon in eine [geoJSON](https://geojson.org)-Datei.
"Leider" ist die [so gefundene Bahnhofstrasse](https://www.openstreetmap.org/way/27405455) die als Fläche erfasste Fussgänger-zone am Bahnhof in Zürich und nicht ganz das was wir suchen.
Mit [kurzer Nachhilfe](https://mastodon.social/@habi/111364288036273018) von Amanda können wir den Aufruf durch `-f highway≠pedestrian` erweitern um Trottoirs und Fussgängerzonen auszuschliessen.

Also liefert uns 

````bash
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"[b|B]ahnhof" -o ch-bahnhof.geojson --only-longest-n-per-file 1
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"la [g|G]are" -o ch-gare.geojson --only-longest-n-per-file 1
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"[s|S]tazion" -o ch-stazion.geojson --only-longest-n-per-file 1
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"[s|S]taziun" -o ch-staziun.geojson --only-longest-n-per-file 1
````

die längste 'Bahnhofstrasse', die längste 'Rue de la Gare', die längste 'Via della Stazione' sowie die längste 'Via de la Staziun' jeweils als geoJSON-Datei.
Diese sind als Karte unten eingebunden.

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.osm.ch/en/map/langste-bahnhofstrasse_6326?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.osm.ch/en/map/langste-bahnhofstrasse_6326?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true">See full screen</a></p>
Die längste *Bahnhofstrasse* der Schweiz mit 3.14 km in Unterneuhaus (am Rand der Schweiz).

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.osm.ch/en/map/la-plus-longue-rue-de-la-gare_6327?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.osm.ch/en/map/la-plus-longue-rue-de-la-gare_6327?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true">See full screen</a></p>
Die längste *Rue de la Gare* der Schweiz mit 2.29 km in Sonceboz-Sombeval.

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.osm.ch/en/map/la-via-della-stazione-la-piu-lunga-della-svizzera_6328?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.osm.ch/en/map/la-via-della-stazione-la-piu-lunga-della-svizzera_6328?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true">See full screen</a></p>
Die längste *Via della Stazione* der Schweiz mit 1.69 km in Airolo.

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.osm.ch/en/map/la-lung-via-de-la-staziun_6329?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.osm.ch/en/map/la-lung-via-de-la-staziun_6329?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true">See full screen</a></p>
Die längste *Via de la Staziun* der Schweiz mit 1.05 km in Pontresina.

Das Spiel können wir mit 

````bash
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"[b|B]ahnhof" -o ch-bahnhof-all.geojson
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"la [g|G]are" -o ch-gare-all.geojson
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"la [s|S]tazion" -o ch-la-stazion-all.geojson
./osm-lump-ways -i switzerland-latest.osm.pbf -f highway -f highway≠pedestrian -f name~"la [s|S]taziun" -o ch-la-staziun-all.geojson
````
wiederholen und wir haben dann jeweils *alle* solchen in einer jeweiligen Datei.
Diese alle geoJSON-Dateien schieben wir in eine sogenannte uMap und stellen für jede Sprachregion eine [hübsche Farbe](https://www.learnui.design/tools/data-color-picker.html#palette) ein.
Und Voilà, eine Karte davon ist unten eingebunden zu sehen.

<iframe width="100%" height="300px" frameborder="0" allowfullscreen allow="geolocation" src="//umap.osm.ch/en/map/bahnhof-la-gare-la-stazione-und-la-staziun_5747?scaleControl=false&miniMap=false&scrollWheelZoom=false&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true"></iframe><p><a href="//umap.osm.ch/en/map/bahnhof-la-gare-la-stazione-und-la-staziun_5747?scaleControl=false&miniMap=false&scrollWheelZoom=true&zoomControl=true&editMode=disabled&moreControl=true&searchControl=null&tilelayersControl=null&embedControl=null&datalayersControl=true&onLoadPanel=undefined&captionBar=false&captionMenus=true">See full screen</a></p>
Alle sprachregiongetrennten Bahnhofstrassen, die längste davon jeweils als besonders dick gezeichnet.

[^1]: Die eben als `way` abgebildet werden.
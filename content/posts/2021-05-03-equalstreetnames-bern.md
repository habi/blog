---
author: habi
title: "EqualStreetNames Bern"
slug: equalstreetnames-bern
date: 2021-05-03T22:37:14+02:00
draft: true
categories:
- nerdism
- openstreetmap
- personal
tags:
- opendata
- openstreeetmap
- collaboration
---


![Bärn, i ha di gärn!](/static/2021/Bern.png)

Wer mich ein bisschen kennt, weiss, dass ich einen OpenStreetMap-Fetisch habe.
Letzthin bin ich via [WeeklyOSM](https://weeklyosm.eu/archives/14443#wn560_24766) auf [EqualStreetNames](http://equalstreetnames.be) gestossen.
Das Team von EqualStreetNames visualisiert, wie die Geschlechterverteilung der Strassennamen in einer Stadt aussieht, z.B. für [Brüssel](https://equalstreetnames.brussels/).
Das Team von EqualStreetNames hat [eine Vorlage](https://github.com/EqualStreetNames/equalstreetnames-template) erstellt, damit eine solche Strassenbenamsungsgeschlechterverteilungsvisualisierung für jede beliebige Stadt erstellt werden kann.
Da ich Verknüpfungen von verschiedenen Datenquellen liebe und ’a sucker for nice visualizations’ bin, hab ich mir gedacht, das sollte doch auch für Bern gemacht werden.
Etwas später war die Vorlage [angepasst](https://github.com/EqualStreetNames/equalstreetnames-bern) und noch einen Moment später war https://bern.equalstreetnames.eu/ mit der Ersten nach dem Geschlecht der Namensgeber*in visualisierten Strasse online, der [Hardeggerstrasse](https://overpass-api.de/achavi/?changeset=103203212).

Vor einer Woche hab’ ich dann ein paar OpenStreetMap-Aktive in Bern angeschrieben, ob sie mithelfen, die Strassen mit den notwendigen (und richtigen) [`name:etymology:wikidata`](https://wiki.openstreetmap.org/wiki/Key:name:etymology:wikidata)-Tags zu versehen, damit diese Strassen dann in der Visualisierung auftauchen.
Dieser Tag beschreibt die Namensgeber*in in maschinenlesbarer Form, so dass automatisch das Geschlecht ausgelesen und visualisiert werden kann.

Eine Woche später haben mindestens [thisss](http://osm.org/user/thisss), [ydrgbjo](http://osm.org/user/ydrgbjo), [freaktechnik](http://osm.org/user/freaktechnik), [chatelao](http://osm.org/user/chatelao) und [orycteropus1](http://osm.org/user/orycteropus1) (sortiert in Reaktionszeitreihenfolge) mitgeholfen, dass von 908 Strassennamen in Bern schon 177 mit dem `name:etymology:wikidata`-Tag versehen sind [1].

Das Resultat der Arbeit ist hier zu sehen: [EqualStreetNames.Bern](https://bern.equalstreetnames.eu/).

Von den 177 Strassen, die bis jetzt eine*r Namensgeber*in zugeordnet sind, sind 151 nach einem Mann und 24 nach einer Frau benannt.
Die restlichen 731 Strassen sind entweder nach irgendwas sonst benannt, oder wurden noch nicht richtig zugeordnet.

Wer mithelfen möchte, am Repository für Bern rumzubasteln, oder dasselbe für ’seine’ Stadt nachzubauen möchte, kann sich gerne direkt bei mir melden.

[1]: Teilweise sogar mit zwei solchen Tags, wie die [Tschäppätstrasse](https://www.openstreetmap.org/way/249724883), die nach beiden Tschäppäts benannt ist.

PS1: chatelao hat von einer Bekannten aus der Politik eine Liste mit allen Strassenbeschilderungungen aufgetrieben, die wir mit Quellenangabe "Geodaten Stadt Bern” verwenden dürfen und in [eine Tabelle](https://docs.google.com/spreadsheets/d/15dDGMJSa0HdUemPqakue229IPZydJl1pMS2FPgCgoCA/edit#gid=0
) abgefüllt.

PS2: ydrgbjo hat eine [Wikimedia Commons-Kategorie](https://commons.wikimedia.org/wiki/Category:Street_signs_in_Bern) erstellt; er und ich befüllen diese mit Strassenschilder-Fotos, damit unser Tagging nachvollziehbar ist.

PS3: Das [Interdisziplinäre Zentrum für Geschlechterforschung der Uni Bern](https://www.izfg.unibe.ch) hat es in den zwei vergangenen Wochen noch nicht mal geschafft auf meine Mail-Anfrage nach Strassennamengeschlechteraufteilung zu reagieren, auch wenn der [Barbara-Lischetti-Platz](https://www.openstreetmap.org/way/665047918/) direkt vor deren Tür liegt :

PS4: Das Bild mit den Strassen von Bern im Header habe ich schnell mit der Hilfe von [`osmnx`](https://geoffboeing.com/2016/11/osmnx-python-street-networks/) und dessen [Beispiel-Notebook 7](https://mybinder.org/v2/gh/gboeing/osmnx-examples/main) gemacht...
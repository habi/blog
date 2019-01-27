---
author: admin
comments: true
date: 2014-02-05 23:14:32+00:00
link: http://habi.gna.ch/2014/02/06/das-mitmach-web-ist-tot/
slug: das-mitmach-web-ist-tot
title: Das Mitmach-Web ist tot!
wordpress_id: 3374
categories:
- fun
- technospeak
tags:
- comments
- kommentare
- python
- visualization
---

Vor [fast zwei Jahren](http://habi.gna.ch/2012/03/31/wohin-gehen-all-die-kommentare-visualisiert/) haben das Thema schon mal diskutiert; und befunden dass bei verschiedenen Blogs bei den Kommentaren die Peaks überschritten sind.

Letzthin fiel mir ein, dass ich das doch mal wieder anschauen wollte, ob sich daran etwas geändert hat. Nach kurzer Analyse komm ich zur Aussage, dass das Mitmach-Web tot ist, jedenfalls aus meiner Sicht. Auf meinem Blog hier hab' ich den letzten drei Jahren Kommentarzustände wie 2006, also im Schnitt ca. anderthalb Kommentare pro Eintrag.
Dafür kann es mehrere Gründe geben, der offensichtlichste ist, dass das was ich schreibe generell wenig Reaktionen hervorruft. Ein anderer Grund ist, dass sich kein Schwein für das interessiert, was ich schreibe. Oder dass generell nicht mehr so kommentiert wird, wie vor einigen Jahren.

Das tönt jetzt etwas griesgrämig, ist aber nicht wertend gemeint. Wenn ich das, was ich hier mache nur machen würde, um Rückmeldungen abzuholen, bin ich sowieso auf der falschen Schiene. Das Blog hier dient schon über 10 Jahren (jawoll) als öffentliches Tagebuch, zum festhalten von Eindrücken und Dingen, die mich bewegen.

Und schliesslich sind Blogs nur noch für 40-jährige mit Kindern, wie Herr Kottke [letzthin schrieb](http://www.instapaper.com/read/440629888). Beide Eigenschaften treffen (noch) nicht wirklich auf mich zu, ihr wisst aber schon, worauf ich raus will.

Langer Rede kurzer Sinn; ich hab' mich mal wieder hinter die Tastatur geklemmt und versucht, ein kleines Skript zu schreiben, welches mir die Arbeit abnimmt, die Aussagen aus der Datenbank zu knübeln, damit ich das Gegreine oben mit Zahlen belegen kann.

Ich hab' das Skript von vor zwei Jahren etwas ausgebaut, so dass das Datenbank-Gepfriemel und die Anzeige in einem Rutsch gehen. Und zwar so.

Dank [MySQL Connector/Python](http://dev.mysql.com/doc/connector-python/en/index.html) wird die Datenbank von WordPress direkt angezapft, mit [optparse](http://docs.python.org/2/library/optparse.html) werden dem Skript ein paar Vorgaben (Server, Datenbank, Username und Passwort) dazu übergeben.


Die Datenbank-Abfrage (ursprünglich von [Herr Leu](http://leumund.ch/wohin-gehen-all-die-kommentare-0014184)) wird direkt übergeben.


Anschliessend wird mit den abgefragten Daten etwas jongliert und diese dann ausgegeben, 


Und schlussendlich wird mit [matplotlib](http://matplotlib.org) das ganze visuell dargestellt und als Bild gespeichert, Dank [iWantHue](http://tools.medialab.sciences-po.fr/iwanthue/) in einer optimalen Farbkombination.
.

Wer das ganze für sich selber auch anschauen möchte, sei herzlichst eingeladen, das Skript [hier herunterzuladen](https://github.com/habi/python/tree/master/comments-visualization) und im Terminal zu starten. Ohne Parameter gibt's mal eine Hilfe, ich verrate schon, dass mensch die Angaben wie Server, Datenbank-Name, -User und -Passwort bereithalten sollte. Wenn du das grad nicht mehr weisst, findest du diese Angaben in deiner [wp-config.php](http://codex.wordpress.org/Editing_wp-config.php)-Datei.

[Issues](https://github.com/habi/python/issues) und Pull Requests sind herzlich willkommen, genauso wie Kommentare mit den Bildern von euch.

[![habi_gna_ch.png](http://habi.gna.ch/wp-content/uploads/2014/02/habi_gna_ch-300x113.png)](http://habi.gna.ch/wp-content/uploads/2014/02/habi_gna_ch.png)

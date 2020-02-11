---
title: Zebrafischkiemen wachsen, wenn die Fische trainieren
date: 2020-02-06T19:00:00.000+00:00
slug: zebrafischkiemen-wachsen-mit-training
categories:
- science
- work
tags:
- work
- zebrafish
- gills
- research
---

In den [letzten Wochen](http://habi.gna.ch/?s=zebrafisch&submit=Search) hab' ich's immer wieder angetönt, ich hatte viel mit Zebrafischen zu tun.
Beim Schaffen hatten wir ein grosses Projekt, bei dem ich die Auswertung von Tomographiedaten (und anderem) übernommen habe, damit wir schlussendlich sicher sagen konnten, dass die Kiemen von Zebrafischen wachsen, wenn die kleinen Fische feste trainieren.

Aber alles der Reihe nach: Wie ihr wisst, arbeite ich seit einiger Zeit am Institut für Anatomie mit zwei MicroCT-Geräten und mache biomedizinische Forschung.
[Zebrafische](https://en.wikipedia.org/wiki/Zebrafish) sind nicht nur härzige Aquariumbewohner, sondern auch ein prima Modellorganismus in der Biologie.
Dies, weil sie unter anderem im Anfangsstadium ihres Lebens durchsichtig sind, also sehr gut geeignet sind um das Organwachstum zum Beispiel unter dem Mikroskop zu untersuchen.
Im Projekt, bein dem ich mitgearbeitet habe ging es auch um das Organwachstum, aber nicht darum, dass das Organ durchsichtig ist.
Wir wollten nämlich prüfen, ob die Kiemen der Zebrafische wachsen, wenn sie ausgiebig trainiert werden.

Dazu wurden die Fische während einigen Wochen von Matthias und Dea in einem sogenannten Schwimmtunnel  trainiert.
Von 20 diesen Fischen haben Oleksiy, Fluri und ich dann hochaufgelöste, röntgentomographische Aufnahmen des Kopfes gemacht.
Aus diesen dreidimensionalen Aufnahmen haben Dea und Matthias dann die Kiemen virtuell ausgeschnitten.
Diese ausgeschnittenen Kiemen habe ich dann in [einem ziemlich langen](https://github.com/habi/zebra-fish-gills) [Jupyter Notebook](https://jupyter.org/) analysiert, so dass wir schlussendlich [zum Schluss](https://journals.plos.org/plosone/article/figure?id=10.1371/journal.pone.0228333.g004) gekommen sind, dass die Kiemen der trainierten Fische einerseits grösser und andererseits 'luftiger' werden, d.h. die Abstände zwischen den Ästen der Kiemen grösser sind.

Da ich es *extrem* wichtig finde, dass unsere Resultate nachvollziehbar sind, habe ich versucht meine Arbeit am Projekt so zu machen, dass diese im Stil von [Reproducible research](https://de.wikipedia.org/wiki/Offene_Wissenschaft) von A-Z nachvollziehbar ist.
Die Daten, die Dea und Matthias aus den grossen gescannten Datensätzen digital ausgeschnitten haben, sind bei der OpenScienceFoundation zu finden, sogar mit eigener [DOI:10.17605/OSF.IO/A5ESX](https://doi.org/10.17605/OSF.IO/A5ESX).
Wenn diese 20 Datensätze heruntergeladen [1] und in einem Verzeichnis auf einem Rechner ausgepackt werden, ist ein Grossteil der Daten die es zum Nachvollziehen braucht schon da. Der Rest (Bilder, Excel-Files, etc.) ist alles im [GitHub-Repository](https://github.com/habi/zebra-fish-gills) meiner Analyse zu finden, das also auch 'nur' ausgecheckt werden muss.
Dann muss das Notebook gestartet werden und das Verzeichnis mit den Rohdaten in Zelle 16 des Notebooks angepasst werden. Anschliessend dauert die Berechnung je nach Leistungsfähigkeit des Rechners eine kurze oder lange Weile [2], Zwischenschritte werden jeweils ins oben angepasste Verzeichnis gespeichert, falls mal die Rechenleistung nicht ausreicht...

Schlussendlich habe ich dann die so generierten Bilder und Tabellen ins Manuskript kopiert, welches wir gemeinsam auf [Authorea](https://www.authorea.com/) geschrieben haben.
Mit einem Klick haben wir das Manuskript öffentlich gemacht, und es auf [bioRxiv](https://de.wikipedia.org/wiki/BioRxiv) hochgeladen: [DOI:10.1101/744300](https://doi.org/10.1101/744300).
Das heisst, dass das Manuskript zwar ab dann öffentlich ist, aber dessen Qualität ist noch nicht mit einem sogenannten ['peer review'](https://de.wikipedia.org/wiki/Peer-Review) sichergestellt.
Dafür haben wir das Manuskript bei [PLOS ONE](https://journals.plos.org/plosone/) eingereicht.
Dort wurde dann das Manuskript von uns unbekannten Kennern und Kennerinnen der Materie geprüft, ein paar Dinge bemängelt und nach unseren Korrekturen schlussendlich publiziert: [DOI:10.1371/journal.pone.0228333](https://doi.org/10.1371/journal.pone.0228333).

Weil ich gerne meine Arbeit versuche schön zu zeigen, habe ich dann zum Manuskript aus den Daten noch eine Visualisierung gemacht.
Dieser Film ist unten eingebunden [3].
Die Visualisierung zeigt einen Kopf eines Zebrafisches, den wir gescannt haben.
Das Auge des Zebrafishes hat einen Durchmesser von ungefähr 0.8 mm, der ganze Kopf ist also nicht viel grösser als 5 mm.
Auf der linken Kopfseite wurden die Kiemen entfernt und damit die elektronenmikroskopischen Untersuchungen gemacht.
Auf der rechten Seite des Kopfes tauchen die Kiemen als rotes Volumen auf.

In Zebrafischen sind diese Kiemen als vierblättrige Struktur aufgebaut, die eben mit Training einerseits grösser und andereseits luftiger wird.
Cool, oder?

{{< youtube CMXfyqgaQxs >}}

[1]: Am einfachsten mit diesem kleinen Bash-Skript: https://raw.githubusercontent.com/habi/Zebra-Fish-Gills/master/download.osf.sh

[2]: Mein Bürorechner hat 196 GB RAM und eine [2 TB-NCMe SSD](https://www.pcworld.com/article/2899351/everything-you-need-to-know-about-nvme.html)...

[3]: Da ich den Film nicht direkt von PLOS ONE einbinden konnte, habe ich eine Kopie meines Films auf Youtube hochgeladen.
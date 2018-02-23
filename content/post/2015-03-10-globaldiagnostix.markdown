---
author: admin
categories:
- personal
- work
comments: true
date: 2015-03-10T17:18:23Z
link: http://habi.gna.ch/2015/03/10/globaldiagnostix/
slug: globaldiagnostix
tags:
- globaldiagnostix
title: GlobalDiagnostiX
wordpress_id: 3858
---

Seit [gut zwei Jahren](https://github.com/habi/GlobalDiagnostiX/commits/master) arbeite ich im Rahmen meiner PostDoc-Stelle in der [Röntgen-Tomographie-Gruppe](http://www.psi.ch/lsb-tomography/) am [GlobalDiagnostiX](http://globaldiagnostix.org)-Projekt mit.

Eine Gruppe von mittlerweilen 40 Personen aus jeglichen Fachrichtungen will versuchen, das Problem der medizinischen Bildgebung in Entwicklungsländern zu lösen. Es ist nämlich so, dass zwei Drittel der Menschheit keinen Zugang zu medizinischer Bildgebung haben, sei es Röntgen oder Ultraschall. Genau solche Untersuchungsmethoden sind wichtig, um korrekte diagnostische Entscheide zu treffen.

Die GlobalDiagnostiX-Allianz hat sich zum Ziel gesetzt, dieses Problem zu lösen und entwickelt und baut ein medizinisches Röntgengerät, welches an die Bedingungen in Entwicklungsländern (Klima, Stromversorgung, Kaufkraft) angepasst ist. Das Gerät soll standard-konforme digitale Röntgenbilder liefern und in Spitälern helfen, Patienten besser zu betreuen als dies heute möglich ist.

Der Detektor des Systems ist das Puzzle-Teil des Systems, zu welchem ich beigetragen habe. Weil klassische Film-Röntgenbilder veraltet sind und heutzutage verwendete [Flat panel Detektoren](http://enwp.org/Flat_panel_detector) zu teuer und fehleranfällig sind, um in diesen Regionen sicher eingesetzt zu werden, haben wir versucht, die Röntgenstrahlen nach dem Patienten mit einfachen Mitteln in ein digitales Röntgenbild umzuwandeln.

Einfach gesprochen werden die Röntgenstrahlen nach dem Patienten oder der Patientin von einer aktiven Schicht in sichtbares Licht umgewandelt, welches von einem kleinen Haufen Kameras abfotografiert wird. Nach ausgiebiger Vorarbeit und einer Testphase habe ich zusammen mit einem [Master-Studenten](http://www.ti.bfh.ch/en/weiterbildung/weiterbildungsangebote/mas/medizintechnik.html) verschiedenste Komponenten evaluiert und im Rahmen der gegebenen Spezifikationen die beste Zusammenstellung aus aktiver Schicht, Linsen und Fotoapparaten (um bei der einfachen Sprache zu bleiben) bestimmt. Ein Elektroniker der [Fachhochschule Yverdon](http://www.iai.heig-vd.ch/) hat uns die Ideen so implementiert, dass selbst ich als Physiker einfach mit den einzelnen Kameras arbeiten konnte. All das zusammengesetzt in einer Kiste (um bei der einfachen Sprache zu bleiben) die eine Master-Studentin aus Lausanne gebaut hat ist dann schlussendlich eines der Puzzleteile, welches zusammen ein Röntgengerät werden. Dieses Röntgengerät haben wir Ende letztes Jahr zusammengebaut, getestet und am 15. Januar damit das erste Röntgenbild gemacht.

Das Ganze sieht dann im Imagefilm der EPFL so aus:

http://youtu.be/MoRxh_r4nyQ

Nach ausgiebigen Tests, einigen Umbauten und vielen neuen Dingen auf unserer ToDo-Liste war's dann gestern soweit; die Allianz hat das System mit einem Event an der EPFL präsentiert. Das Medienecho ist eine schöne Bestätigung unserer Arbeit; Das Schweizer Fernsehen hat darüber berichtet, Keystone-Fotografen waren da, heute las' ich im Bund eine [Notiz darüber auf der Wissens-Seite](https://www.evernote.com/shard/s2/sh/b63f9654-dbd8-47e6-814d-cf94f458c6e4/71ec14d34d27134bb54751d50e5199f7), die [EPFL hat auf ihrer Startseite](http://actu.epfl.ch/news/finally-x-ray-imaging-within-the-reach-of-developi/) Informationen zum Projekt aufgeschaltet.

Ich muss gestehen, es macht mich ziemlich stolz, wenn der Aufhänger des unten eingebundenen RTS-Beitrages (ca. nach 10 Sekunden) etwas ist, an dem ich in den letzten Wochen gearbeitet habe.



Wer genau zuschaut, kann auch sehen, wie ich im Beitrag meinem Scheff die Details der FlatField-Korrektur und dem Zusammensetzen der digitalen Mosaikbilder erläutere, nach ca. 40 Sekunden.

Genau so stolz bin ich, dass wir alle, die an diesem Projekt mitgearbeitet haben, diesen Meilenstein erreicht haben.

Und jetzt; "[back to the lab!](https://www.youtube.com/watch?v=aCV0pHjtxes)", es gibt noch viel zu tun!

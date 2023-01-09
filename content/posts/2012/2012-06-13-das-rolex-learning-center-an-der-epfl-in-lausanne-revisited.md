---
comments: true
date: 2012-06-13 20:45:10+00:00
link: https://habi.gna.ch/2012/06/13/das-rolex-learning-center-an-der-epfl-in-lausanne-revisited/
slug: das-rolex-learning-center-an-der-epfl-in-lausanne-revisited
title: Das Rolex Learning Center an der EPFL in Lausanne, revisited
wordpress_id: 2798
categories:
- pictures
- technospeak
tags:
- epfl
- hugin
- lausane
- pannellum
- panorama
- webstandards
---

Vor ein paar Wochen war [arbeitsmässig](http://globaldiagnostix.org/) wieder mal an einer Sitzung in Lausanne. Wie schon das letzte Mal hat mich das [Rolex Learning Center](http://www.rolexlearningcenter.ch/) in seinen Bann gezogen, dieses Mal hatte ich aber meine Panorama-Ausrüstung dabei, und nicht wie das [letzte Mal](https://habi.gna.ch/2012/01/20/rolex-learning-centre/) nur mein Telefon.




Dabei ist die Einsicht unten entstanden.




  

Die geneigte Leserin und der geneigte Leser wird merken, dass das Panorama direkt von meinem eigenen Webserver kommt (genauer von panoramas.davidhaberthür.ch) und nicht von 360cities oder so.  

Kürzlich hat [Matthew Petroff](http://www.mpetroff.net/) auf der hugin-Panorama-Mailingliste von seinem neuesten Goodie erzählt, er hat nämlich einen modernen Panoramaviewer programmiert; [Pannellum](http://www.mpetroff.net/?p=547).  

Pannellum ist ein kleines Skript, welches auf den eigenen Server kopiert Panoramas ohne mühsames Flash-Plugin immersiv darstellt. Das heisst, das Panorama wird mit der Hilfe von neuen Web-Standards (HTML5, [WebGL](https://de.wikipedia.org/wiki/WebGL), etc.) aufgebaut und dem User ausgeliefert, und sollte in jedem modernen Browser funktionieren. Je nach Browser muss der WebGL-Support eingeschaltet werden (in Safari hab' ich's [so gemacht](http://cl.ly/HM9I), für andere Browser geht's [so](http://www.khronos.org/webgl/wiki/Getting_a_WebGL_Implementation)), leider geht's momentan auf iTelefonen und iTablets nicht.  

Die Konfiguration und Bereitstellung eines Panoramas ist dank dem mitgelieferten Konfigurator relativ einfach, hat aber noch ein paar eingebaute Hindernisse. Da der Quellcode des Skriptes aber auf [bitbucket offen zur Verfügung](https://bitbucket.org/mpetroff/pannellum/overview) steht, werde ich versuchen, diese Hürden für mich abzubauen und Matthew davon zu berichten, so dass weitere User diese Hürden nicht überwinden müssen.  

Wer die restlichen Panoramas, die ich in Lausanne gemacht habe sehen will, soll seinen Browser [hierhin](http://fotos.davidhaberthür.ch/index.php?type=sets&setId=72157630121439668) dirigieren.

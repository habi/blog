---
title: Die (Gmeinde)Grenzen der Schweiz
date: 2026-03-07T12:11:10.000+00:00
slug: recommended-readings-MONAT-2025
categories:
- openstreetmap
tags:
- openstreetmap
- vibe coding
draft: yes
---

Ihr wisst ja, ich hab' einen OpenStreetMap-Fetisch :)
Schon *sehr* lange trage ich gemeinsam mit der Schweizer OSM-Community die Idee rum, dass die ~2000 erfassten Gemeindegrenzen in OpenStreetMap besser gepflegt werden sollten.

Diese wurden vor [~14 Jahren](https://www.openstreetmap.org/user/SwisstopoImports/history#map=8/46.796/8.262&layers=SN) in einem sogenannten [Import](https://wiki.openstreetmap.org/wiki/DE:Import) in die OpenStreetMap-Datenbank eingepflegt und seither bei Gemeindefusionen Anfangs Jahr immer mal wieder gepflegt, aber nicht *in toto* überwacht.

Vor einiger Zeit habe ich im [OSM Forum die Diskussion zur Grenzpflege](https://community.openstreetmap.org/t/update-des-13-jahrigen-imports-der-swissboundaries3d-grenzen/118604) begonnen, das dort angesprochene [Tool der serbischen Community](https://gitlab.com/osm-serbia/prostorne-jedinice-import) ist zwar *sehr* toll, aber der Umbau auf die Schweizerischen Gegebenheiten hat nicht befriedigend geklappt.
Dies trotz der tollen Hilfe der [SOSM](https://sosm.ch) mit einer virtuellen Maschine (mersi [Datendelphin](https://www.openstreetmap.org/user/datendelphin) im Speziellen) auf der SOSM-Infrastruktur.
Auf dieser VM lief das serbische Tool mit Anpassungen für die Schweiz, war aber nur schwer zu "bedienen".

In einem Projekt bei der Arbeit habe ich mich etwas eingehender mit den sog. [GitHub Actions](https://docs.github.com/en/actions) beschäftigt, mit denen es möglich ist, ja nach Zustand eines GitHub-Projektes Aktionen durchzuführen, die ebenso auf einer virtuellen Infrastruktur (aber halt von Microsoft laufen).
Eine solche Action baut beispielsweise aus etwas LaTeX-Code, der online liegt automatisch meinen [Lebenslauf](https://habi.github.io/cv/cv.pdf) (ich hab' keine Bewerbung offen, brauchte aber letzthin aus anderen Gründen einen Lebenslauf).
Oder aus [etwas Textschnipseln](https://github.com/habi/sticklebacks-manuscript/tree/main/content) eine [Webseite](https://habi.github.io/sticklebacks-manuscript/) und ein [PDF](https://habi.github.io/sticklebacks-manuscript/manuscript.pdf), das eine Pubikation ergeben wird. 

Item, Programmcode im Internet etwas machen zu lassen, ist mit solchen Actions einfach, schnell iterierbar und etwas weniger komplex, als per [`ssh`](/https://en.wikipedia.org/wiki/Secure_Shell) auf einem Server Python-Code laufen zu lassen.

Um die Gmeindegrenzen in OpenStreetMap zu überwachen habe ich jetzt nicht Programmiercode im Netz zum laufen gebracht, sondern diesen Programmiercode *nicht* selber geschrieben.
Das geht mit sog. [vibe coding](https://en.wikipedia.org/wiki/Vibe_coding) gemacht.
Zu Beginn habe ich das [Large Language Model](https://de.wikipedia.org/wiki/Large_Language_Model) von [Claude.ai](https://claude.ai/) mit einem Prompt gefüttert, der beschreibt, was ich machen will.

> I have the boundaries of the swiss municipalities in https://data.geo.admin.ch/ch.swisstopo.swissboundaries3d/swissboundaries3d_2025-04/swissboundaries3d_2025-04_2056_5728.gpkg.zip.
> Help me produce a report on how well these match geographically with the boundaries mapped in OpenStreetMap, preferrably via Overpass Turbo.
> The boundaries in the geopackage have `bfs_nummer=355`, the boundaries in OSM have `swisstopo:BFS_NUMMER=355` as a matching ID.

> Can you query Overpass in Python, too?

> Can you make this all work in a GitHub action?

Das heisst, ich habe Claude informiert, dass die Gemeindegrenzen der Schweiz in OpenStreetMap in sogenannten Relationen mit z.B. `swisstopo:BFS_NUMMER"=355` für [Köniz](https://www.openstreetmap.org/relation/1682518) erfasst sind.
Die BFS_NUMMER wird vom Bundesamt für Statistik vergeben und taucht genauso in den offiziellen Gemeindegrenzen von swisstopo, [swissBOUNDARIES3D](https://www.swisstopo.admin.ch/en/landscape-model-swissboundaries3d) auf.
Ich hätte die Abfrage der Gemeindegrenzen gerne mit [Overpass turbo](https://wiki.openstreetmap.org/wiki/DE:Overpass_turbo) abgefragt, den Vergleich in Python gemacht und das Ganze per GitHub Action z.B. täglich laufen gelassen.
Schon [die erste Antwort](https://github.com/habi/swissboundaries/commit/b44bc00c88c278f4f7a17ebe1cd128721b5478f4) von Claude lieferte Resultate, die ich dann in [VS Code mit CoPilot](https://code.visualstudio.com/docs/copilot/overview) mit vielen Prompts immer weiter verfeinert habe.
Ich habe nur *extrem* wenig Code selbst geschrieben, praktisch Alles wurde gesteuert durch meine Eingaben maschinell erstellt, minimalste Zwischenschritte wurden [von Anderen](https://github.com/habi/swissboundaries/pulls?q=is%3Apr+is%3Aclosed) beigesteuert.





Review durch Community-Members, Issue von Simon auch durch LLM korrigiert.



- Vibe coding: *keine* Zeile alleine geschrieben
- TIGER: Verweis auf Simons diary post
- Diskussion mit Seen, Tessin
- Was kommt noch (Löcher/Enklaven)?

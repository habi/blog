---
date: '2024-11-25T20:35:58+01:00'
title: 'Tchüss Evernote, es war gut.'
categories:
- technospeak
tags:
- evernote
- reading
- recommended readings
- linkdump
---

Evernote hat seit Ende Juli 2008 ziemlich viele Dinge für mich aufbewahrt.
Über die Jahre habe sich dort Rezepte, Notizen, Links, kopierte Zitate aus gelesenen Texten, Audio-Dateien mit lustigen Aufnahmen (und Erklärungen zu Kinderzeichnungen), Code-Schnipsel und Screenshots aufbewahrt, die ich nicht nur auf meinem Rechner aufbewahren wollte, sondern auch auf dem Telefon und manchmal im Büro brauchte.

Über die Jahre wurde Evernote immer teurer und der Funktionsumfang wurde trotzdem immer mehr beschnitten, zuletzt war es nicht mehr möglich, mit mehr als 3 Geräten die Notizen synchron zu halten, wobei das Web-Interface auch als Gerät zählte.
Einer der Use-Cases war auch das Teilen von Familien-wichtigen Dingen mit Nina, was mit Evernote Anfangs easy möglich war, aber immer komplizierter wurde, und neuderdings nur noch mit einem Account möglich, der 15$ pro Monat kostet.

Eine Zeitlang haben Nina und ich versucht, mit Joplin warm zu werden, was aber für geteilte Notizbücher mit PDFs und Bildern auch mehr als 10 $ im Monat kostet.

Seit längerem störte mich auch das Kuddel-Muddel in Entweder Evernote oder Joplin, dass - wie erwähnt - Dokumente, Screenshots, Textnotizen, Scans von Kinderzeichnungen wild durcheinander quasi auf einem Haufen lagen.
Klar immer schön mit Titeln und Schlagworten versehen, aber die Suche nach gesuchten Dingern war eher mühsam.

Nachdem ich mal über [Paperless](https://docs.paperless-ngx.com) gestolper bin, habe ich lange prokrastiniert, ob ich mir jetzt doch mal ein NAS kaufen und das Ding darauf installieren soll.
Als ich dann mal in anderem Zusammenhang von [elest.io](https://elest.io) gelesen habe, die es *extrem* simpel machen, irgendwo eine virtuelle Maschine zu starten und darauf praktisch irgendwelche Software zu installieren.
Zwei und zwei zusammengezählt, und schon habe ich (dank einer DNS-Weiterleitung) eine Instanz von `paperless-ngx` unter http://paperless.davidhaberthuer.ch am Laufen.
Diese Instanz kostet mich zwar knapp 9$ im Monat, ist aber a) billger als Evernote, hat b) einen erstaunlich grossen [WAF](https://de.wikipedia.org/wiki/Woman_acceptance_factor) und ist c) in den paar Monaten wo ich das jetzt am Laufen habe genau das Richtige. :)
Die Software schluckt jegliche Art von Dokument (präferiert aber PDFs) und kann sogar tiptop mehrere User:innen verwalten, so dass auch Nina Ihre Dokumente, die auf mehreren Geräten zu Brauchen sind dort einfach hinterlegen kann.
Durch die Texterkennung und Verschlagwortung kann in *jedem* hochgeladenen Dokument gesucht werden und dank einem [minimal-aufwändigen Workflow](https://docs.paperless-ngx.com/usage/#usage-recommended-workflow) und einem Hochleistungs-Scanner im Büro hab' ich grad noch einiges an Dokumenten zuhause digitalisiert und physisch entsorgt.

Damit nun *alle* +1500 Notizen aus Evernote am richtigen Ort landeten, habe ich [`evernote-backup`](https://github.com/vzhd1701/evernote-backup) angeworfen.
Mit dieser Software und

```bash
evernote-backup init-db --oauth
evernote-backup sync
evernote-backup export --include-trash EverNoteBackup
```
landete jede Evernote-Notiz erstmals auf meinem Rechner.
Theoretisch wäre ein Export aus Evernote auch möglich, aber neuerdings können im Gratis-Account nur noch 50 Notizen angeschaut werden, und selbt in Bezahl-Accounts nur noch 100 Notizen aufs Mal exportiert werden.

Mit [`enex2paperless`](https://github.com/kevinzehnder/enex2paperless) ([via  [reddit.com](https://www.reddit.com/r/selfhosted/comments/120mmo1/comment/kjy5hbg/)]) landete dann jedes Dokument das möglich ist, in meiner Paperless-Installation.
Nachdem die Zugangsdaten in dern Konfigurations-Datei gespeichert waren, funktionierte der Prozess mit

```bash
for i in EverNoteBackup/*.enex;do echo ./enex2paperless $i; done 
```
problemlos.
Dieser Import-Prozess führte zu einigen Warnungen, dass die virtuelle Maschine unter Volllast laufe, da in paperless für jedes Dokument [OCR](https://de.wikipedia.org/wiki/Texterkennung) durchgeführt wird :)

So landeten mal alle *Dokumente* am richtigen Ort.
Da aber eben auch viele Links, Code-Schnipsel, Zitate und weitere Nicht-Dokumente im Evernote waren, habe ich ganz simpel *alle* exportierten Evernote-Dateien in [Simplenote](https://simplenote.com) reingeladen, das geht einfach mit ['drag-and-drop'](https://simplenote.com/2018/11/29/bring-all-your-notes-home-with-the-new-import).
Simplenote ist auch so eine App, die ich schon länger am Start habe, dort landeten aber ausschliesslich *nur* Text-Schnipsel.

Jetzt muss ich nur noch durch den grossen Haufen durchsortieren, was aber (v.a. in Simplenote) eigentlich einfach ist.

- Notizen, die nur "application/pdf", "image/jpeg", "image/png" enthalten, sind Dokumente, die schon im Paperless landeten, also einfach löschen.
- *Viele* Rezepte, die sich angesammelt haben, landen dank gespeichertem Link und exzellenter Importfunktion in [Mela](https://mela.recipes/). In Simplenote einfach nach Migusto, Chefkoch, Ottolenghi, Wildeisen und den Link zu Mela teilen, dann kommt's gut. Mela ist übrigens eine super Rezepte-Verwaltungs- und auch Koch-App, von Silvio-[Reeder]-Rizzi, die jeden Rappen der 5 Franken wert ist.
- Die Suche nach 'http' findet Links, die dann einfach zu [Pinboard]( https://pinboard.in/u:habi) kopiert werden.
- Die Suche nach 'Instapeper' findet viele markierte Zitate, für die ich momentan noch nix besseres als einen [Tag bei Pinboard](https://pinboard.in/u:habi/t:quote).

Ihr seht, Evernote ganz loszuwerden ist ganz einfach :)
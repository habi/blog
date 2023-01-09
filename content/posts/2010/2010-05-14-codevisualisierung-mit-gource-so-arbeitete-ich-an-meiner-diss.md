---
date: 2010-05-14 20:49:05+00:00
link: https://habi.gna.ch/2010/05/14/codevisualisierung-mit-gource-so-arbeitete-ich-an-meiner-diss/
slug: codevisualisierung-mit-gource-so-arbeitete-ich-an-meiner-diss
title: Codevisualisierung mit Gource - So arbeitete ich an meiner Diss
wordpress_id: 2125
categories:
- technospeak
- tschörman
---

Meine Diss ist auf der Post, im Moment heisst's nur noch warten, was die beiden Korrigierenden dazu meinen.
Anschliessend gibt's noch einiges zu tun bis Ende Juni, wenn ich meinen Diss-Vortrag halten muss.
Aber im Moment hab' ich etwas mehr Zeit zum rumspielen.

Genau das habe ich gestern gemacht.
Als [Typo-Nerd](https://google.com/images?hl=en&client=safari&rls=en&q=i%20shot%20the%20serif&um=1&ie=UTF-8&source=og&sa=N&tab=wi) habe ich meine Diss in [LaTeX](http://www.latex-project.org/) geschrieben und den Fortschritt zusätzlich in einem [Subversion](https://en.wikipedia.org/wiki/Apache_Subversion)-Repository festgehalten.
Dies auch damit ich jederzeit zu einer älteren Version zurückwechseln könnte, wäre es denn nötig gewesen.
Kürzlich bin ich über die faszinierenden Code-Visualisierungen gestossen, die mit [Gource](http://code.google.com/p/gource/) gemacht werden können.
Wenn mann versucht, meine Arbeit an meiner Diss zu visualisieren, sieht das dann so aus:

{{< vimeo 11716626 >}}

Da für das Ganze doch einiges an rumprobieren notwendig war (und weil vielleicht andere das auch versuchen wollen: [This](http://www.borniert.com/), der Blick geht zu dir, ich nehme an, du hast für deine [Semesterarbeit](http://www.borniert.com/2010/05/10/lizenziatsarbeit-zeitung-der-zukunft/) sicher auch irgendwie versioniert :))

Die Installation von Gource ist unter OS X dank [MacPorts](http://www.macports.org/) [1] schnell erledigt: Ein Aufruf des untenstehenden Befehls in Terminal.app installiert das Commandline-Programm mit allen Zugehörigkeiten.

````bash
sudo port install gource
````

Falls du auf deiner Maschine [Git](http://git-scm.com/) und [ffmpeg](http://www.ffmpeg.org/) [2] noch nicht installiert hast, dann machst du das Ganze in einem Aufwasch am besten mit 

````bash
sudo port install git ffmpeg gource
````

Je nach Aktualität deiner MacPorts-Installation braucht's vorher evtl. noch ein "sudo port selfupdate", damit alles klappt.
Am besten machst du dir jetzt ein Kafi oder so, das Ganze kann längere Zeit dauern.

Anschliessend gibts du in einem leeren Verzeichnis (immernoch im Terminal) den Befehl

````bash
git svn clone http://svn.ana.unibe.ch/svn/Thesis-David
````

ein.
Dies hat zur Folge, dass via Git ein Subversion-Repository (keine Angst, das Repository ist nur innerhalb der Uni Bern erreichbar :) ) ausgecheckt wird.
Gource arbeitet nur mit Git-Repositories zusammen, was aber dank "git svn clone" problemlos klappt.

Das oben eingebundene Filmli habe ich dann mit

````bash
cd Thesis-David
gource -1280x720 --disable-progress --stop-at-end --bloom-multiplier 1.25 --bloom-intensity 1 -a 0.25 --output-ppm-stream - | ffmpeg -y -b 3000K -r 60 -f image2pipe -vcodec ppm -i - -vcodec libx264 -vpre default Thesis.mp4
````
erstellt.
Am besten trinkst du jetzt deinen Kafi fertig, das Ganze kann wieder etwas dauern.
Obiger Befehl berechnet das Filmli mit Gource in HD-Auflösung (`-1280x720`), ohne Progress-Bar, hört am Ende auf, ändert die Darstellung etwas (`-bloom-multiplier`, `-bloom-intensity` und `-a`) und schreibt das ganze in einen [PPM](https://en.wikipedia.org/wiki/Netpbm_format#PPM_example)-Stream.
Dieser Stream wird dann mit ffmpeg direkt in das Filmli Thesis.mp4 umgewandelt.
Hochladen zu vimeo, fertig!

[1]: MacPorts ist sowieso uneingeschränkt zu empfehlen, jegliche Opensource-Software lässt sich so extrem einfach installieren.
[2]: Dringend nachholen, am besten auch gerade noch ImageMagick, dann konvertierst du easy Bilder und Videos...

PS1: Hat jemand gemerkt, dass ich diesen Eintrag dank Gratis-WLAN in Atlanta, Georgia, USA geschrieben habe?
Ich bin 10 Tage in den USA, benehmt euch also!

PS2: Das war wohl der bisher nerdigste Beitrag ever hier!

---
title: "Im 2020 habe ich 3 Millionen Schritte gemacht"
slug: 
date: 2021-02-04T21:54:03+01:00
categories:
- jahresrückblick20
- jahresrückblick
tags:
- jahresrückblick20
- jahresrückblick
- steps
- python
- seaborn
- quantifiedself
---

Apropos [`seaborn`](https://habi.gna.ch/2021/02/04/recommended-readings-vom-januar-2021/); Hier einer der Posts zu meinem 2020.
Dieser und andere Posts sind unter dem Tag [`jahresrückblick20`](https://habi.gna.ch/tag/jahresruckblick20) zu finden.

Wie Anfangs 2019 habe ich mal wieder auf meine Schritte geschaut.
Im 2020 habe ich 3.03 Millionen Schritte gemacht.
Das weiss ich, weil ich die Schrittzahlen, die meine Uhr aufnimmt, über Garmin Connect in Apple Health ablegt, via einer App in ein Textfile exportiert habe.
Das CSV-File lässt sich mit [etwas Python-Code](https://github.com/habi/steps) kurz anschauen, so dass ich eben weiss, dass ich pro Tag im 2020 im Schnitt gut 8000 Schritte machte (im 2018 waren's noch +10000...).

Wie damals ist schön zu sehen, dass ich am <del>Mittwoch</del>Papatag eher mehr Schritte mache.

![Schritte pro Wochentag](https://habi.gna.ch/wp-content/uploads/2021/02/output_19_0.png)

Die Ferien- und 'ausschliesslich HomeOffice'-Monate tauchen auch verstärkt in der "Statistik" auf (die eben dank `seaborn` so aussieht).

![Schritte pro Monat](https://habi.gna.ch/wp-content/uploads/2021/02/output_20_0.png)

Wer sich für den kompletten Code interessiert, findet das Jupyter Notebook [hier auf GitHub](https://github.com/habi/steps), oder [klickt hier für eine lauffähige Version des Notebooks auf Binder](https://mybinder.org/v2/gh/habi/steps/master).

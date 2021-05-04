---
author: admin
comments: true
date: 2008-11-04 23:35:29+00:00
link: https://habi.gna.ch/2008/11/05/evolution-einer-abbildung-oder-wieso-einfach-wenns-kompliziert-einfacher-ist/
slug: evolution-einer-abbildung-oder-wieso-einfach-wenns-kompliziert-einfacher-ist
title: 'evolution einer abbildung oder: wieso einfach, wenn''s kompliziert einfacher
  ist'
wordpress_id: 1527
categories:
- personal
- technospeak
---

ich bin am skizzieren einer publikation, meine [masterarbeit](http://www.ana.unibe.ch/~haberthuer/publications) des nachdiplomstudiums soll zu einem richtigen paper werden.




dafür braucht es natürlich abbildungen, um das ganze ein wenig anschaulich zu machen. ich habe währen meiner masterarbeit eine methode entwickelt, wie das sichtfeld von - höchstauflösender - tomographie so erweitert werden kann, dass der benutzer die wahl zwischen einer schnellen aufnahme mit ok-qualität und einer aufnahme in höchster qualität, dafür dauert das dann aber länger. das ganze wird erreicht, indem die tomographie-aufnahmen speziell zusammengestellt werden. je nach position der probe müss eine unterschiedliche anzahl aufnahmen gemacht werden. ist auch nicht extrem wichtig, ich wollte einfach mal aus dem nähkästchen plaudern, und zeigen, was ich heute nami im büro gemacht habe.




während der masterarbeit am [PSI](http://www.psi.ch/) habe ich unter [linux](https://en.wikipedia.org/wiki/Scientific_Linux) [xfig](http://www.xfig.org/) als zwar altmodisches, aber extrem [potentes](http://www.xfig.org/art9.html) zeichenprogramm kennengelernt. meine erste idee war deshalb, die abbildung mithilfe von [jfig](http://tams-www.informatik.uni-hamburg.de/applets/jfig/) zu erstellen, einer java-implementation von jfig, die auch per [webstart](http://tams-www.informatik.uni-hamburg.de/applets/jfig/webstart.html) ohne installation gestartet werden kann [1].




diese idee wurde dann kurz nach diesem ergebnis abgebrochen, weil's einfach zu kompliziert wurde mit dem zeichnen der verschiedenen projektionen in verschiedenen winkeln...




(der klick auf die screenshots macht's gross)



  [![evolution.jfig.png](https://habi.gna.ch/wp-content/uploads/2008/11/evolutionjfig.jpg)](https://habi.gna.ch/wp-content/uploads/2008/11/evolutionjfig.png)



als nächstes kam dann eines meiner lieblings-vektor-zeichen-programme zum zug; [inkscape](http://inkscape.org/). ein zeichen-programm, das auch [viel kann](http://commons.wikimedia.org/wiki/Category:Created_with_Inkscape). dadurch, dass sich jedes objekt in der grösse manipulieren lässt und dass winkel händisch eingegeben werden können, habe ich gedacht, sei das bildli schnell gezeichnet. nachdem ich dann meinen taschenrechner mit cosinus und sinus gequält habe, und das bild immer noch nicht wirklich gut aussah, habe ich aufgegeben. immerhin sieht das bild schon ein bisschen besser aus als oben und dank der guten export-funktion würde die abbildung im end-dokument auch gut aussehen.



  [![evolution.inkscape.png](https://habi.gna.ch/wp-content/uploads/2008/11/evolutioninkscape.jpg)](https://habi.gna.ch/wp-content/uploads/2008/11/evolutioninkscape.png)



irgendwann kam dann der geistesblitz: am einfachsten wäre es wohl, das ganze statt in 2D mühsam zu zeichnen, schnell in 3D als szene zu erstellen, damit's mit allen winkeln und ansichten stimmt. also mal [blender](http://www.blender.org/) installiert, nachdem dies durch einen befreundeten [roboter](http://nothing.ch/company/team/spot) empfohlen wurde [2]. blender ist ein 3D-programm, das extrem viel kann, wie mensch in der [galerie](http://www.blender.org/features-gallery/gallery/art-gallery/) sehen kann. wem [elephants dream](http://orange.blender.org/download) oder [big buck bunny](http://www.bigbuckbunny.org/index.php/download/) ein begriff sind, weiss, dass mit blender auch filme gemacht werden können, [sinnfreie](http://download.blender.org/demo/movies/gallery/bouncetospace.avi) (8MB) oder auch extrem [eindrückliche](http://download.blender.org/demo/movies/gallery/meischeid.mov) (58MB!).




nachdem die ersten schritte dank des ungewohnten interfaces von blender sehr wackelig waren, konnte ich nach etwa einer halben stunde ein bild machen, an dem ich morgen weiterarbeiten kann. das licht und die schatten müssen noch korrigiert werden, und ob ich das bild in ein vektor-format exportieren kann, weiss ich auch noch nicht. sonst rendere ich den aufbau der projektionen einfach in HD, dann merkts keiner, wenn ich's runterskaliere. und an den farben arbeite ich auch noch...



  [![evolution.blender.png](https://habi.gna.ch/wp-content/uploads/2008/11/evolutionblender.jpg)](https://habi.gna.ch/wp-content/uploads/2008/11/evolutionblender.png)



manchmal lohnt es sich also, einen komplizierten umweg zu gehen, auch wenn der weg nicht unbedingt das ziel ist.einfach so, damit ihr wisst, was ich den ganzen tag so im büro mache...




[1]: übrigens ist webstart meine lieblingsvariante zum starten von [jabref](http://jabref.sourceforge.net/jws/jabref.jnlp) und [imageJ](http://rsbweb.nih.gov/ij/ImageJ.jnlp) auf allen möglichen systemen...  

[2]: der nebst firmen führen auch noch [filme generiert](http://border-the-movie.com/), dies aber dann in maya und nicht mit blender...  





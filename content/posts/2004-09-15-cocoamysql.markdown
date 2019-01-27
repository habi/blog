---
author: admin
comments: true
date: 2004-09-15 10:59:18+00:00
link: http://habi.gna.ch/2004/09/15/cocoamysql/
slug: cocoamysql
title: CocoaMySQL
wordpress_id: 617
categories:
- none
---

since i've been doing a lot o database maintenance lately (you won't believe how many errors can be produced when [84 persons register themself](http://suicmc04.ch/registration/english.php)...) i was looking for an easy way to do it.
The whole registration process for the [suicmc04](http://www.suicmc04.ch/) runs on a [MySQL database](http://www.mysql.com/) on the gna-server (thanks b. and chris for hosting us!). 
Äbu, who did all the backend programming for us installed [phpMyAdmin](http://www.phpmyadmin.net/home_page/) on the server, which is quite a good way to tinker with the database, but i didn't like it that much. so i was looking for another way to get to the data. [dbSuite Admin Tool](http://www.dbsuite.de/) is a well renowned Software to connect to your database which i used up to now. But yesterday evening i found the best tool up to now!

[![cocoamysql](http://habi.gna.ch/blog/images/cocoamysql-tm.jpg)](http://habi.gna.ch/blog/images/cocoamysql.jpg)[CocoaMySQL](http://cocoamysql.sourceforge.net/) is the tool i'll be using from now on. It's available for free and under the GPL license which means the app and it's source code are free (but you might want to donate a buck or two). 
In addition to that it's also a lot spiffier than dbSuite Admin and phpMyAdmin, you can browse the database very fast and managing the database and editing the values is a breeze. And because you can decide to show the console you learn all those MySQL-terms, so maybe once i'll be able to do all this via the command line :-)

if you ever need to remotely manage a database (and need a GUI to do it, like i do) then you should give it a try with CocoaMySQL!

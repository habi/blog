---
author: admin
comments: true
date: 2012-06-21 19:38:19+00:00
link: https://habi.gna.ch/2012/06/21/sonderzeichen-probleme/
slug: sonderzeichen-probleme
title: Sonderzeichen-Probleme
wordpress_id: 2820
categories:
- technospeak
---

Als ich letzthin jemandem das Filmli über [Terry Pratchett](https://habi.gna.ch/2011/12/08/sir-terry-pratched-will-sterben/) zeigen wollte, hab' ich im Archiv hier gegraben.
Dabei ist mir aufgefallen, dass mein ganzes Wordpress-Archiv von einem komischen Sonderzeichen-[Käfer](http://en.wikipedia.org/wiki/File:H96566k.jpg) befallen war, alle Sonderzeichen wurden nicht mehr in der UTF8-Codierung angezeigt, sondern jedes ä, ö und ü war durch Ã¤, Ã¶ und Ã¼ ersetzt.

Nach einer kürzeren Suche nach möglichen Problem-Ursachen hab' ich dank der Hilfe von [Mastblau](http://www.mastblau.com/2009-01-20/wordpress-auf-utf-8-umstellen/) rausgefunden, dass ich mit einer Datenbank-Befehl alle fehlerhaften Einträge korrigieren kann.
Mit der Hilfe von [Sequel Pro](http://www.sequelpro.com/) hab' ich untenstehende Änderungen an meiner Wordpress-Datenbank gemacht, so dass das Archiv wieder mit korrekten Umlauten dargestellt werden sollte (und momentan wird).
Falls jemand in der nächsten Zeit trotzdem irgendwelche Probleme bemerkt, soll er/sie sich bitte bemerkbar machen...

````sql
update wp_posts set post_content = replace( post_content,'Ã¼','ü');
update wp_posts set post_content = replace( post_content,'Ã¤','ä');
update wp_posts set post_content = replace( post_content,'Ã¶','ö');
update wp_posts set post_content = replace( post_content,'ÃŸ','ß');
update wp_posts set post_content = replace( post_content,'Ãœ','Ü');
update wp_posts set post_content = replace( post_content,'Ã„','Ä');
update wp_posts set post_content = replace( post_content,'Ã–','Ö');
update wp_posts set post_title = replace( post_title,'Ã¼','ü');
update wp_posts set post_title = replace( post_title,'Ã¤','ä');
update wp_posts set post_title = replace( post_title,'Ã¶','ö');
update wp_posts set post_title = replace( post_title,'ÃŸ','ß');
update wp_posts set post_title = replace( post_title,'Ãœ','Ü');
update wp_posts set post_title = replace( post_title,'Ã„','Ä');
update wp_posts set post_title = replace( post_title,'Ã–','Ö');
update wp_comments set comment_content = replace( comment_content,'Ã¼','ü');
update wp_comments set comment_content = replace( comment_content,'Ã¤','ä');
update wp_comments set comment_content = replace( comment_content,'Ã¶','ö');
update wp_comments set comment_content = replace( comment_content,'ÃŸ','ß');
update wp_comments set comment_content = replace( comment_content,'Ãœ','Ü');
update wp_comments set comment_content = replace( comment_content,'Ã„','Ä');
update wp_comments set comment_content = replace( comment_content,'Ã–','Ö');
update wp_term_taxonomy set description = replace( description,'Ã¼','ü');
update wp_term_taxonomy set description = replace( description,'Ã¤','ä');
update wp_term_taxonomy set description = replace( description,'Ã¶','ö');
update wp_term_taxonomy set description = replace( description,'ÃŸ','ß');
update wp_term_taxonomy set description = replace( description,'Ãœ','Ü');
update wp_term_taxonomy set description = replace( description,'Ã„','Ä');
update wp_term_taxonomy set description = replace( description,'Ã–','Ö');
update wp_tags set tag = replace( tag,'Ã¼','ü');
update wp_tags set tag = replace( tag,'Ã¤','ä');
update wp_tags set tag = replace( tag,'Ã¶','ö');
update wp_tags set tag = replace( tag,'ÃŸ','ß');
update wp_tags set tag = replace( tag,'Ãœ','Ü');
update wp_tags set tag = replace( tag,'Ã„','Ä');
update wp_tags set tag = replace( tag,'Ã–','Ö');
````

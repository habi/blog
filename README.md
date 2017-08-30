# blog

This is a repository containing my blog.
Aeons ago I started with [Movable Type](https://www.movabletype.org/), then switched to [Wordpress](http://wordpress.org).
Now I'd like to take away a ton of dependencies and just let it run by [Jekyll](https://jekyllrb.com/) on [GitHub Pages](http://pages.github.com).

# Steps to export and convert the data

- Export an XML file from http://habi.gna.ch/wp-admin/export.php (gives you habignach.wordpress.2017-08-30.xml as per today).
- `git clone https://github.com/thomasf/exitwp.git ~/Dev/exitwp`
- `cp ~/Dev/*.xml ~/Dev/exitwp/wordpress-xml`
- `cd ~/Dev/exitwp/ && python2 exitwp.py`
- `mv ~/Dev/exitwp/build/jekyll/habi.gna.ch/_posts/* ~/Dev/blog/_posts/'

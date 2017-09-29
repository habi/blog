# habi.github.io

## Info
[![Build Status](https://travis-ci.org/habi/habi.github.io.svg?branch=master)](https://travis-ci.org/habi/habi.github.io)

This is a repository containing my blog.
Aeons ago I started with [Movable Type](https://www.movabletype.org/), then switched to [Wordpress](http://wordpress.org).
Now I'd like to take away a ton of dependencies and just let it run by [Jekyll](https://jekyllrb.com/) on [GitHub Pages](http://pages.github.com).

## Steps to export and convert the data

- Export an XML file from http://habi.gna.ch/wp-admin/export.php (gives you habignach.wordpress.2017-08-30.xml as per today).
- `git clone https://github.com/thomasf/exitwp.git ~/Dev/exitwp`
- `cp ~/Dev/*.xml ~/Dev/exitwp/wordpress-xml`
- `cd ~/Dev/exitwp/ && python2 exitwp.py`
- `mv ~/Dev/exitwp/build/jekyll/habi.gna.ch/_posts/* ~/Dev/habi.github.io/_posts/`

## Start this shizzle
- `cd ~/Dev/habi.github.io && jekyll new . --force`
- Add all files in `_posts` to the Git repository
- Push to GitHub
- Change repository [settings](https://github.com/habi/blog/settings) to enable GitHub Pages for this repository
- Connect to [Travis CI](https://travis-ci.org/habi/habi.github.io), with the details given on [this GitHub page](https://help.github.com/articles/viewing-jekyll-build-error-messages/)

## Test locally
- `bundle install
  - [Fix for the Nokogiri problem](https://stackoverflow.com/a/27496640)
- `jekyll serve`
- Go to [localhost on port 4000](http://localhost:4000)
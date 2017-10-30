# habi.github.io

## Info
This repository contains my blog.

Aeons ago I started with [Movable Type](https://www.movabletype.org/), then switched to [Wordpress](http://wordpress.org).
Now I'd like to take away a ton of dependencies and just let it run by [Jekyll](https://jekyllrb.com/) on [GitHub Pages](http://pages.github.com).

After thinking some more, I find [Hugo](http://gohugo.io) in combination with [Netlify](https://netlify.com/) an even more compelling solution.

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
- We then have a running Jekyll site at [habi.github.io/](https://habi.github.io)

## Convert to Hugo

- Move all the Jekyll stuff (from this repository) to a temporary folder
- `hugo import jekyll ~/Dev/temporary-folder/ ~/Devhabi.github.io/ --force`
- `cd ~/Dev/habi.github.io/themes`
- Add a theme with `cd themes && git submodule add ThemeURL`, since Netlify doesn't support the usual `gut clone ThemeURL` way of installing Hugo themes.

# Host this thing (automatically)
- Follow [this guide](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
- Set up DNS, e.g. set the following in the admin panel of cyon
    blog CNAME very-fancy-strings-with-numbers.netlify.com
    

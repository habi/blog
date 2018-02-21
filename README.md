# blog.davidhaberthuer.ch
## Info
This repository contains my blog.

Aeons ago I started with [Movable Type](https://www.movabletype.org/), then switched to [Wordpress](http://wordpress.org).

After wanting to remove a ton of dependencies and headaches I tried running it by [Jekyll](https://jekyllrb.com/) on [GitHub Pages](http://pages.github.com).

After putting some more thoughts on it, I found [Hugo](http://gohugo.io) in combination with [Netlify](https://netlify.com/) an even more compelling solution.
This means that - in theory - I'm free to move this thing to any host I want and still have the blog running from this repository.

## Steps to export and convert the data to a Jekyll site

- Export an XML file from http://habi.gna.ch/wp-admin/export.php (gives you habignach.wordpress.2018-02-21.xml as per today).
- `git clone https://github.com/thomasf/exitwp.git ~/Dev/exitwp`
- `cp ~/Dev/*.xml ~/Dev/exitwp/wordpress-xml`
- `cd ~/Dev/exitwp/ && python2 exitwp.py`
- `mv ~/Dev/exitwp/build/jekyll/habi.gna.ch/_posts/* ~/Dev/blog/_posts/`

The exoprted posts are geared toward a 'Jekyll' site, but also work with 'hugo'.

## Convert to Hugo

- Move all the Jekyll stuff (from this repository) to a temporary folder
- `mv ~/Dev/exitwp/build/jekyll/habi.gna.ch/_posts/* ~/Dev/blog/content/post/`
- `cd ~/Dev/blog/themes`
- Add a theme with `cd themes && git submodule add ThemeURL`, since Netlify doesn't support the usual `git clone ThemeURL` way of installing Hugo themes.

# Host this thing (automatically)
- Follow [this guide](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
- Set up DNS, e.g. set the following in the admin panel of cyon.
  Netlify tells us to do `blog CNAME very-fancy-strings-with-numbers.netlify.com`
    

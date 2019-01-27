# My blog
Aeons ago I started with [Movable Type](https://www.movabletype.org/), then switched to [Wordpress](http://wordpress.org).
Now I'd like to take away a ton of dependencies and just let it run by a [static site generator](https://www.staticgen.com).

At the moment, [Hugo](http://gohugo.io) in combination with [Netlify](https://netlify.com/) seems like a compelling solution to simplify my life.

# Steps to export and convert the data
- Export an XML file from the [WordPress admin interface](http://habi.gna.ch/wp-admin/export.php).
  Probably you only want the posts, not everything.
- Clone the [exitwp](https://github.com/thomasf/exitwp) repository by issuing `git clone https://github.com/thomasf/exitwp.git ~/Dev/exitwp` in your terminal.
  This piece of fine software converts a WordPress export to a bunch of [Markdown](https://daringfireball.net/projects/markdown/) files and also grabs (most of) the images.
- Copy the exported XML file to the path where `exitwp` would like to have it: `cp ~/Downloads/*.xml ~/Dev/exitwp/wordpress-xml`
- Run `exitwp`: `cd ~/Dev/exitwp/ && python2.7 exitwp.py` (If you set `download_images: True` in `config.yaml` you should also get (most of) the images).
- You now get an export of the site in `~/Dev/exitwp/build/jekyll/habi.gna.ch`.

# Get up and running
- Start a new hugo site with `cd ~/Dev && hugo new site blog --force`.
  This only has to be done the first time...
- `cd blog`
- `git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke`
- `echo 'theme = "ananke"' >> config.toml`
- Edit `config.toml` to taste.
- Now unzip the `hugo-export.zip` file from above.
- Copy all the posts from the exported directory to the `blog` directory: `mkdir -p ~/Dev/blog/content/posts && cp ~/Dev/exitwp/build/jekyll/habi.gna.ch/_posts/* ~/Dev/blog/content/posts/`
- Copy all the images from the `exitwp` directory to the `blog` directory: `mkdir -p ~/Dev/blog/static/images && cp ~/Dev/exitwp/build/jekyll/habi.gna.ch/images/*/*.* ~/Dev/blog/static/images/`. We move the images from their subfolder to a single new folder.
- Now you should have a (semi)working hugo blog, test it with `cd ~/Dev/blog && hugo server`. All images are still served from their original URLs.

# Host this thing (automatically)
- Follow [this guide](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/)
- Set up DNS, e.g. set the following in the admin panel of cyon.
  Netlify tells us to do `blog CNAME very-fancy-strings-with-numbers.netlify.com`
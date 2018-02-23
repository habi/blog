---
author: admin
categories:
- gadgets and gizmos
- technospeak
comments: true
date: 2009-04-10T19:51:26Z
link: http://habi.gna.ch/2009/04/10/panoramas-from-low-quality-movies/
slug: panoramas-from-low-quality-movies
tags:
- cycoder
- hugin
- imagej
- iphone
- panorama
title: panoramas from (low quality) movies [update]
wordpress_id: 1722
---

whenever i'm spending a day outdoor, i love to take pictures, many of them turn out to be [panoramas](http://www.flickr.com/photos/habi/tags/panorama).

sometimes i leave my camera at home and only have my [mobile phone](http://www.apple.com/iphone/) with me. shoothing panoramas with the iphone is possible with [panolab](http://linktoapp.com/panolab) [link opens itunes], but very cumbersome. and i try to keep the annoyance of nina as low as possible while stopping on the slopes, so fiddling with my phone for longer than a minute or two is not an option.

recently i was thinking about a quick-and-dirty way of creating panorams with the iphone: wouldn't it be possible to extract the images of a movie shot while panning the scenery and stitch those together to generate a panorama? today was the perfect way to test this out, on the slopes of the wonderful [stockhorn](http://habi.gna.ch/2009/04/10/der-wohl-letzte-skitag-der-with-map/).

the whole process is fairly easy, you only need




    
  * an iphone, [jailbroken](http://howto.wired.com/wiki/Jailbreak_an_iPhone_3G) (or any other movie source :) ) with [cycoder](http://cydia.saurik.com/info/cycorder/) installed

    
  * [cyberduck](http://cyberduck.ch/) or [winscp](http://winscp.net/), depending on your platform

    
  * [imageJ](http://rsbweb.nih.gov/ij/) and

    
  * [hugin](http://hugin.sourceforge.net/)



all these - very fine - pieces of software are freely available, most of them even free as in beer and as in speech.

**step 1:
shoot a movie.**

**below are the movies i've used for this tutorial. both are made with the excellent cycoder.app, only for jailbroken iphones. use any other movie if you don't have an iphone :) the movies are 384x288 pixels in size, as shown below, just press the play-button.**

https://www.flickr.com/photos/habi/3429965750/

https://www.flickr.com/photos/habi/3429970486/

**step 2:**
get the movies off your iphone.

cyberduck and SFTP are my weapons of choice, [YMMV](http://www.urbandictionary.com/define.php?term=ymmv), but there are tons of tutorials on the web, here's one for the [mac](http://www.appleiphoneapps.com/2008/08/how-to-ssh-sftp-a-walkthrough-for-mac-users/) and here's one for [windows](http://www.appleiphoneapps.com/2009/03/accessing-files-on-your-iphone-a-guide-to-sshsftp-for-windows-users-jailbreak/).
now you should have some movies on your hard-disk. cycoder has the nice feature to produce quicktime-compatible .mov-files, if you don't have one of those handy, again, YMMV. (use the excellent [handbrake](http://handbrake.fr/) to convert [to and fro](http://www.dict.cc/?s=to+and+fro)). quicktime is nice for the next step.

**step 3:**
import the movies into imageJ.

if you're on a mac, this is just simple drag-and-drop, on windows you might be quicker altogether if you convert your movies to .avi-files, since installing quicktime for java can be a bit of a [hassle](http://www.google.com/search?client=safari&rls=en-us&q=imageJ+quicktime+windows&ie=UTF-8&oe=UTF-8), but can be done.

this opens your quicktime movie as a stack of images you can then scroll through. this image-stack can then easily be exported as an image-sequence using "File > Save as > Image Sequence...". rotate the images if you've been dumb enough to hold the iphone wrong :)

then you'll have a bunch of single images on your harddisk. if you've panned quite slowly like i have done, you're probably gonna have much too many images (167 for the first and 139 for the second movie) to easily stich a panorama. for these movies, i've removed some images from the stack using the [slice remover plugin](http://rsbweb.nih.gov/ij/plugins/slice-remover.html). remove slices that are unnecessary like the ones at the beginning and the end, where your glove covers the lens. now having 20 and 32 images from both movies, proceed to the next step.

**step 4:**
import the images from the step above into hugin, align and stitch.

yes, that's it, it's really that [easy](http://wiki.panotools.org/Hugin_Assistant_tab). for the movies shown above i've also deleted some bad control points and stitched the panoramas normally and enfused, but this is entirely optional.the end-result looks like the images below. click them to see them bigger.



[![stockhorn_panorama1_fused.jpg](http://habi.gna.ch/wp-content/uploads/2009/04/stockhorn-panorama1-fused1.jpg)](http://habi.gna.ch/wp-content/uploads/2009/04/stockhorn-panorama1-fused.jpg)
[![stockhorn_panorama2.jpg](http://habi.gna.ch/wp-content/uploads/2009/04/stockhorn-panorama21.jpg)](http://habi.gna.ch/wp-content/uploads/2009/04/stockhorn-panorama2.jpg)







i know that both panoramas are not perfect. both are quite small, especially the second one has some artifacts and both have varying exposure. but keep in mind that i've only bothered nina for 29 seconds, the total time of both movies. not too shabby!

**update:**

arru from sweden left a [comment](http://habi.gna.ch/2009/04/10/panoramas-from-low-quality-movies/comment-page-1/#comment-12364) about extracting the frames of videos using [VLC](http://www.videolan.org/vlc/), which is great, because it plays pretty much any movie-format.

since i couldn't find it, i asked him to outline it for me via email. he agreed that i share his howto, which you can find below:


<blockquote>Extract frames in VLC:

> 
> 
    
>   * Open VLC preferences, select "all" (as opposed to "basic")
> 
    
>   * Go to _Video_->_Output modules_
> 
    
>   * Select '_Image video output'_ (this must be reverted to '_standard'_ when you're done, to use VLC as a normal video player again)
> 
    
>   * Flip down the subgroup next to _Output modules and select '_Image file'__
> 
    
>   * Choose _'PNG'_ as _format_ (JPEG works too, but there will be some unnecessary quality loss)
> 
    
>   * Set _'recording ratio'_ to 10 (determines the number of video frames skipped between images - may need to experiment with this value if images don't overlap correctly)
> 
    
>   * Press _'save'_ to exit VLC preferences
> 
    
>   * Open and play the video in question as you normally would (notice: there will be no picture - sound however, if applicable, and the VLC controls will move to show you the progress of the conversion)
> 
    
>   * Images are saved to the root of the main HDD on Mac OS X ( / ), on Windows I can only assume it will be C:
> 
    
>   * Don't forget to reset step 2 to 'Standard' when you're done
> 
    
>   * Throw images into Hugin and run one of the autopano scripts, and so forth
> 
    
>   * 

</blockquote>


Thanks for that info, Arru!



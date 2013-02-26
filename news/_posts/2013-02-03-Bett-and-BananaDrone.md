---
layout: post
category: News
title: 'Bett and BananaDrone'
---

This week, we attended the 2013 [Bett show](http://www.bettshow.com) and helped [Stephen Heppell](http://heppell.net) on the Learning Together stand.  
We were invited by [Tom Stacy](https://www.twitter.com/Code_ED) to help teach kids [Scratch](http://scratch.mit.edu/) and [Python](http://www.python.org/).  
![A small Scratch program being controlled using Bananas.](img/scratch-bananas.jpg)

<!--break-->

Kids were coming on to our stand having never even seen code before working through Scratch and leaving having written a small story in Python!  
![A short story made with python.](img/python-story.jpg)

We also had some generic little cars that could be controlled over Bluetooth by an Android tablet, kids were then able to use a Javascript-like language to control them.  
![Bluetooth cars being controlled by an Android tablet.](img/bluetooth-cars.jpg)

On the stand, there was an incredibly large display, we had people tell Stephen that they remembered a time when the computers were that big and the screen was as small as the Pi!  
![A large screen for a small computer.](img/big-pi-screen.jpg)

During all of this, [Richard](/members/richardr) was hard at work, mostly trying to get [Nodejs](http://www.nodejs.org) to work on the [Raspberry Pi](http://www.raspberrypi.org).  
Why? Well we had an idea, what if we could fly Tom's [Parrot AR.Drone 2.0](http://ardrone2.parrot.com/) using bananas and the [MakeyMakey](http://www.makeymakey.com)?  
Well that's exactly what we did.  
![Richard controlling an AR.Drone from a command line.](img/bananadrone-in-action.jpg)

###How BananaDrone works
It's all quite simple actually, the AR.Drone creates a WiFi access point that we then connect to using a borrowed Airport Express, the ethernet from the Airport Express then goes into the Raspberry Pi.

![MakeyMakey board connected up to four bananas.](img/makeybananas.jpg)

For control, we had the kids hook up four bananas to the arrow keys on the MakeyMakey board, when you held the ground wire and touched a banana, it would complete a circuit and the MakeyMakey would send a keypress to the Pi.

On the software side, we used [Nodejs](http://www.nodejs.org) along with the [ar-drone](https://github.com/felixge/node-ar-drone) and [keypress](https://github.com/TooTallNate/keypress) libraries.  
The code that goes from keypress to ar-drone was written at about 1AM the day before and is up on [Richard's GitHub](https://github.com/NekomimiScience/Banana-drone).

###Problems faced
As with any project, there were a few issues along the way, for starters, we had faital issues with Node on the Raspberry Pi and had to use Richard's MacBook Pro to get things tested.  
![Nodejs failing to run.](img/node-fail.jpg)  
We eventually found the issue.

<blockquote>
  <p>OH, we're using the soft-float Debian, this is compiled for hard-float!
  <cite>Richard</cite></p>
</blockquote>

So after reimaging the Raspberry Pi's SD card to use hard-float Debian, Node ran correctly and everything was working except the network.  
We had originally planned to get the AR.Drone to join our network but quickly gave up on that after discovering that we couldn't set the timeout long enough for it to connect with all of the wireless access points in the hall also on 2.4Ghz.  
After borrowing an Airport Express and configuring that, BananaDrone was finally ready for takeoff!

We even attracted the attention of Rob Bishop from the Raspberry Pi foundation!  
![Richard and Rob with a Model A Raspberry Pi](img/richard-and-rob.jpg)  
(Yes that's a model A Pi, no we did not get one.)

###Videos!

####Command line testing using a Mac
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/G_BJ-xwGzrA" frameborder="0" allowfullscreen></iframe>
</div>

####Command line testing on the Raspberry Pi
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/ClMjevPWeIY" frameborder="0" allowfullscreen></iframe>
</div>

####BananaDrone fully working
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/XfC4RvgQTJE" frameborder="0" allowfullscreen></iframe>
</div>

####Same from another angle
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/c3SnecpXTS0" frameborder="0" allowfullscreen></iframe>
</div>

####Second flight
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/muzVxcOZFGM" frameborder="0" allowfullscreen></iframe>
</div>

####Networking issues
<div class="flex-video widescreen">
  <iframe width="560" height="315" src="http://www.youtube.com/embed/XmQTzxvua3Q" frameborder="0" allowfullscreen></iframe>
</div>
<blockquote>
  <p>I hate ifconfig, whenever you're looking at ifconfig something's going wrong and you want to be connected to the internet.
  <cite>Rob Bishop</cite></p>
</blockquote>

###Other posts about BananaDrone
- [SkylonRow.co.uk](http://skylonrow.co.uk/2013/02/03/raspberry-pi-at-the-bett-show/)  
- [RotorWorld](http://rotorworld.co.uk/the-bananadrone-combines-quadrocopters-with-banana-control/)
- [CodeED](http://code-ed.blogspot.com/2013/02/learning-together-at-bett-show.html)
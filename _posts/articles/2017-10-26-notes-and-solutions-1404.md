---
layout: article
title: "Notes, solutions for ubuntu 14.04"
categories: [articles, en]
modified: 2017-10-26T23:11:40-04:00
tags: [ubuntu 14.04]
excerpt: "Notes for ubuntu 14.04."
comments: true
ads: false
share: true
author: alex_putz
image:
  teaser: notes_and_solutions_1404.png
---
<img src="{{ site.url }}/images/notes_and_solutions_1404.png">

I will collect some notes on this page while using 14.04, it will be useful for me.
---
Qt couldnt find Mesa headers:

	QtGui/qopengl.h:122:21: fatal error: GL/gl.h: No such file or directory
	#  include <GL/gl.h>

Solution:
Installation of required packages.
```css
sudo apt-get install build-essential libgl1-mesa-dev
```
---
The folder with ruby gems was owned by root, and it prevented users gems instalation.

	ERROR: While executing gem ... 
	(Gem::FilePermissionError) You don't have write permissions 
	into the /var/lib/gems/1.9.1 directory. 

Solution:
Ownership transfer to the current user.
```css
sudo chown -R $(whoami) /var/lib/gems/1.9.1/
```
---
Ruby 2.4 installation on ubuntu 14.04:
```css
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update
sudo apt-get install ruby2.4
```
---
Ruby couldnt find headers while trying to install gems:

	mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h

Solution :
Ruby headers installation for ubuntu 14.04.
```css
sudo apt-get install ruby-dev
sudo apt-get install ruby2.4-dev
```
---
Virtualbox hasnt access to usb devices of the computer.
Grant virtualbox linux access to usb devices of the pc:
```css
sudo usermod -a -G vboxusers $(whoami)
```
---
Viber was making noise while using video/audio call function.

Solution : 

```css
sudo nano /etc/pulse/default.pa

load-module module-udev-detect <--- this entry
```

edit to :
```css
load-module module-udev-detect use_ucm=0 tsched=0
```
and then execute:
```css
killall pulseaudio; rm -r ~/.config/pulse*
```
Restart Viber.
---
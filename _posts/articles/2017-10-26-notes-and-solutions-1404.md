---
layout: article
title: "Notes, solutions for ubuntu 14.04"
categories: [articles, en]
modified: 2017-10-26T23:11:40-04:00
tags: [ubuntu 14.04]
excerpt: "Notes for ubuntu 14.04."
comments: false
ads: false
share: true
author: alex_puts
image:
  teaser: notes_and_solutions_1404.png
---
<img src="{{ site.url }}/images/notes_and_solutions_1404.png">

I will collect some notes on this page while using 14.04, maybe it will help you.
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
sudo chown -R $(whoami) /var/lib/gems/
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
sudo apt-get install ruby-dev ruby2.4-dev
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

Opera browser doesn't start:

	[1220/222332.597277:FATAL:nss_util.cc(632)] NSS_VersionCheck("3.26") failed. 
	NSS >= 3.26 is required.
	Please upgrade to the latest NSS, 
	and if you still get this error, contact your distribution maintainer.
	#0 0x000001eb6ed7 <unknown>
	#1 0x000001ecc3f1 <unknown>
	#2 0x0000023bdff6 <unknown>
	#3 0x0000022f9fd5 <unknown>
	#4 0x00000229c038 <unknown>
	#5 0x0000021ff443 <unknown>
	#6 0x0000006a46ca <unknown>
	#7 0x0000006a4632 <unknown>
	#8 0x000000793313 <unknown>
	#9 0x000000caad5d <unknown>
	#10 0x000001f13170 <unknown>
	#11 0x000001f0deb3 <unknown>
	#12 0x7fac7588b184 start_thread
	#13 0x7fac6f195ffd clone


Solution(libnss3 packages reinstallation):
```css
sudo apt-get install --reinstall libnss3
```
---

Completely remove Libreoffice:
```css
sudo apt-get remove --purge libreoffice*
sudo apt-get clean
sudo apt-get autoremove
```
---

Install all packages in the folder (for examle Libreoffice) execute this in packages folder:

```css
sudo dpkg -i *
```
---


Mime types error:

	Unknown media type in type 'all/all'
	Unknown media type in type 'all/allfiles'
	Unknown media type in type 'uri/mms'
	Unknown media type in type 'uri/mmst'
	Unknown media type in type 'uri/mmsu'
	Unknown media type in type 'uri/pnm'
	Unknown media type in type 'uri/rtspt'
	Unknown media type in type 'uri/rtspu'

Solution:
```css
sudo mv -vi /usr/share/mime/packages/kde.xml /usr/share/mime/packages/kde.xml.bak
sudo update-mime-database /usr/share/mime
```
---

Change ownership of folder and all files in it:
```css
sudo chown -R <username> <path>
```

ubuntu 14.04 \ linux mint 17 no sound, alsa and headers reinstallation is needed.
```css
sudo apt-get install build-essential linux-headers-`uname -r` alsa-base alsa-firmware-loaders alsa-oss alsa-source alsa-tools alsa-tools-gui alsa-utils alsamixergui
sudo apt-get --purge autoremove linux-headers-`uname -r` && sudo apt-get install linux-headers-`uname -r`
```

---

ASIX 88772 USB Ethernet Adapter on Ubuntu 14.04 Linux

Assumes you have another net connection on this machine. 

Download the driver on another machine and copy over if not.

	mkdir asix
	cd asix
	wget http://www.asix.com.tw/FrootAttach/driver/AX88772C_772B_772A_760_772_178_LINUX_DRIVER_v4.20.0_Source.tar.gz
	tar xvzf *
	cd AX88772C_772B_772A_760_772_178_LINUX_DRIVER_v4.20.0_Source
	sudo apt-get install module-assistant
	sudo module-assistant prepare
	sudo modprobe -r asix
	make
	sudo make install
	sudo modprobe asix

Your USB network interface should now come up automatically.

[The original for ubuntu 10.10](https://plugable.com/2010/10/18/howto-asix-88178-usb-ethernet-adapter-on-ubuntu-10-10-linux/)

[Alternative driver download link](https://github.com/AlexPuts/alexputs.github.io/raw/master/files/AX88772C_772B_772A_760_772_178_LINUX_DRIVER_v4.20.0_Source.tar.gz)

---

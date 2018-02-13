---
layout: article
title: "Заметки, решения для ubuntu 14.04"
categories: [articles, ru]
modified: 2017-10-26T23:11:40-04:00
tags: [ubuntu 14.04]
excerpt: "Заметки для ubuntu 14.04."
comments: true
ads: false
share: true
author: alex_putz
image:
  teaser: notes_and_solutions_1404.png
---
<img src="{{ site.url }}/images/notes_and_solutions_1404.png">

При использовании системы ubuntu 14.04 соберу на этой странице решения, пригодится в дальнейшем.
---
Qt не мог найти хедеры Mesa:

	QtGui/qopengl.h:122:21: fatal error: GL/gl.h: No such file or directory
	#  include <GL/gl.h>

Решение:
Установка необходимых пакетов.
```css
sudo apt-get install build-essential libgl1-mesa-dev
```
---
Папка с гемами руби принадлежала руту, что соответственно не позволяло пользователю устанавливать свои гемы в папку.

	ERROR: While executing gem ... 
	(Gem::FilePermissionError) You don't have write permissions 
	into the /var/lib/gems/1.9.1 directory. 

Решение:
Передача прав владения папкой текущему пользователю.
```css
sudo chown -R $(whoami) /var/lib/gems/
```
---
Установка руби 2.4 на ubuntu 14.04:
```css
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update
sudo apt-get install ruby2.4
```
---
Руби не мог найти хедеры при попытке установить гемы:

	mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h

Решение :
Установка хедеров руби на ubuntu 14.04.
```css
sudo apt-get install ruby-dev ruby2.4-dev 
```
---
Virtualbox не имел доступа к usb устройствам компьютера.
Дать virtualbox linux доступ к usb устройствам пк:
```css
sudo usermod -a -G vboxusers $(whoami)
```
---
Viber посторонние звуки при использовании функции видео/аудио звонка.

Решение : 

```css
sudo nano /etc/pulse/default.pa

load-module module-udev-detect <--- эту строчку
```

исправить и дополнить до:
```css
load-module module-udev-detect use_ucm=0 tsched=0
```
далее выполнить:
```css
killall pulseaudio; rm -r ~/.config/pulse*
```
Перезапустить viber.

---
Opera browser не стартует:

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


Решение(переустановка пакетов libnss3):
```css
sudo apt-get install --reinstall libnss3
```
---

Полное удаление Libreoffice:
```css
sudo apt-get remove --purge libreoffice*
sudo apt-get clean
sudo apt-get autoremove
```
---

Установка всех пакетов (например Libreoffice) выполнить в директории с пакетами :

```css
sudo dpkg -i *
```
---


Ошибки mime типов:

	Unknown media type in type 'all/all'
	Unknown media type in type 'all/allfiles'
	Unknown media type in type 'uri/mms'
	Unknown media type in type 'uri/mmst'
	Unknown media type in type 'uri/mmsu'
	Unknown media type in type 'uri/pnm'
	Unknown media type in type 'uri/rtspt'
	Unknown media type in type 'uri/rtspu'

Решение:
```css
sudo mv -vi /usr/share/mime/packages/kde.xml /usr/share/mime/packages/kde.xml.bak
sudo update-mime-database /usr/share/mime
```
---

Изменение прав владения со всеми вложенными файлами:
```css
sudo chown -R <username> <path>
```

ubuntu 14.04 \ linux mint 17 пропадает звук, требуется переустановка альсы и заголовков.
```css
sudo apt-get install build-essential linux-headers-`uname -r` alsa-base alsa-firmware-loaders alsa-oss alsa-source alsa-tools alsa-tools-gui alsa-utils alsamixergui
sudo apt-get --purge autoremove linux-headers-`uname -r` && sudo apt-get install linux-headers-`uname -r`
```

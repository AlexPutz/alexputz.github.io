---
layout: article
title: "Заметки, решения для ubuntu 14.04"
categories: [articles, ru]
modified: 2017-10-26T23:11:40-04:00
tags: [ubuntu 14.04]
excerpt: "Заметки для ubuntu 14.04"
comments: true
ads: false
share: true
author: alex_putz
image:
  teaser: notes_and_solutions_1404.png
---
<img src="{{ site.url }}/images/notes_and_solutions_1404.png">

При использовании системы ubuntu 14.04 соберу на этой странице решения, пригодится в дальнейшем.

Qt не мог найти хедеры Mesa:

	QtGui/qopengl.h:122:21: fatal error: GL/gl.h: No such file or directory
	#  include <GL/gl.h>

Решение:
Установка необходимых пакетов.
```css
sudo apt-get install build-essential libgl1-mesa-dev
```

Папка с гемами руби принадлежала руту, что соответственно не позволяло пользователю устанавливать свои гемы в папку.

	ERROR: While executing gem ... 
	(Gem::FilePermissionError) You don't have write permissions 
	into the /var/lib/gems/1.9.1 directory. 

Решение:
Передача прав владения папкой текущему пользователю.
```css
sudo chown -R $(whoami) /var/lib/gems/1.9.1/
```

Установка руби 2.4 на ubuntu 14.04:
```css
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update
sudo apt-get install ruby2.4
```

Руби не мог найти хедеры при попытке установить гемы:

	mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h

Решение :
Установка хедеров руби на ubuntu 14.04.
```css
sudo apt-get install ruby-dev
sudo apt-get install ruby2.4-dev
```
Virtualbox не имел доступа к usb устройствам компьютера.
Дать virtualbox linux доступ к usb устройствам пк:
```css
sudo usermod -a -G vboxusers $(whoami)
```

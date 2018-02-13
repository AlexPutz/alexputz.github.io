---
layout: article
title: "Notes, solutions"
categories: [articles, en]
modified: 2017-11-11T13:12:22-04:00
tags: [other]
excerpt: "Other useful solutions."
comments: true
ads: false
share: true
author: alex_putz
image:
  teaser: other_solutions.jpeg
---


I will collect solutions for daily tasks on this page it will be useful in the future.

Tenda W311R Router for long time had original chinese firmware and oficical firmwares werent working for it.

<img src="{{ site.url }}/images/tendaw311r.jpg">



Solution:
You should install suiatable firmware.
```css
For Tenda W311R V5.07.31_cn the suitable firmware is V5.07.46_en
```

[Download firmware](https://github.com/AlexPutz/alexputz.github.io/raw/master/files/V5.07.46_en.zip)

[Official page](http://www.tendacn.com/en/download/detail-1798.html)

---

Create bootable windows 7 installation usb in ubuntu linux:
Using standart partition utility(e.g. Gparted or KDE Partition Manager)
1. Delete partition table.
2. Create ntfs partition.
3. Setup boot flag on created partition.

Next:
Create path for image mounting , then mount windows 7 image,
copy image content to prepared flash.
```css
sudo mkdir /media/iso
sudo mount <windows7_image_iso>  /media/iso -t udf -o loop
cp -R /media/iso/* <path_to_flash>
```
---
Configure username and email Git:
```css
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
---

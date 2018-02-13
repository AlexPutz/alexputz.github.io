---
layout: article
title: "Заметки, решения"
categories: [articles, ru]
modified: 2017-11-11T13:12:22-04:00
tags: [other]
excerpt: "Заметки для прочих вещей."
comments: true
ads: false
share: true
author: alex_putz
image:
  teaser: other_solutions.jpeg
---


Соберу на этой странице разнообразные решения для повседневной жизни, пригодится в дальнейшем.

---

Роутер Tenda W311R долгое время был с оригинальной китайской прошивкой, прошивки с официального сайта не устанавливались.

<img src="{{ site.url }}/images/tendaw311r.jpg">



Решение:
Установка подходящей англоязычной прошивки.
```css
Для W311R V5.07.31_cn подходит прошивка V5.07.46_en
```

[Скачать прошивку](https://github.com/AlexPutz/alexputz.github.io/raw/master/files/V5.07.46_en.zip)

[Официальный сайт](http://www.tendacn.com/en/download/detail-1798.html)

---

Запись образа windows 7 на usb в ubuntu linux:
Стандартной утилитой(например Gparted или KDE Partition Manager)
1. Удаляем таблицу разделов.
2. Создаем на флешке раздел ntfs.
3. Устанавливаем на разделе флаг boot.

Далее:
Создаем путь для монтирования образа, монтируем образ windows 7,
копируем содержимое смонтированного раздела (образа) на подготовленную флешку.
```css
sudo mkdir /media/iso
sudo mount <windows7_image_iso>  /media/iso -t udf -o loop
cp -R /media/iso/* <path_to_flash>
```
---
Конфигурирование имени пользователя и имейла Git:
```css
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
---
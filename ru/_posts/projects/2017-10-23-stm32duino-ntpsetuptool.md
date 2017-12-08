---
layout: article
title: "Ntpsetuptool"
categories: [projects, ru]
excerpt: "Программа для настройки ntp сервера точного времени на базе stm32duino/arduino (Qt,C++)."
ads: false
comments: true
share: true
image:
  teaser: ntp_broadcast_setup_tool_ntpservsettings.png
---
<img src="{{ site.url }}/images/ntp_broadcast_setup_tool_ntpservsettings.png">

Данная программа позволяет удобно настраивать сервер точного времени, работающий по протоколу NTP.
Сервер построен на базе stm32duino blue pill, ethernet модуля enc28j60, gps модуля ublox.
Программа позволяет обнаружить сервер в сети, установить ему IP, 
включить/выключить протоколы, просмотреть информацию.
# Ссылки:
[Проект на гитхаб](https://github.com/AlexPutz/stm32dntpsetuptool)

[Проект сервера](https://github.com/AlexPutz/stm32dntp)
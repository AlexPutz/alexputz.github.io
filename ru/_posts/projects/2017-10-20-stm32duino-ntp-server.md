---
layout: article
title: "Stm32duino ntp server"
categories: [projects, ru]
excerpt: "Ntp сервер точного времени на базе stm32duino/arduino."
ads: false
comments: false
share: true
image:
  teaser: stm32dntp_ide.png
---
<img src="{{ site.url }}/images/stm32dntp_ide.png">

Проект сервера точного времени на базе stm32duino.
- Сервер построен на базе stm32duino blue pill, ethernet модуля enc28j60, gps модуля ublox.
- Сервер получает время из gps модуля или из программы для настройки с помощью использования функции "Set time".
- Сервер корректно обрабатывает запросы от систем windows(sntp) linux(ntp).
- Содержит функцию для синхронизации времени по Modbus TCP. ( Содержит регистры Modbus TCP с текущим временем), позволяет синхронизировать с точностью до секунды).

Linux:
```css
sudo ntpdate -d 192.168.0.125
```
<img src="{{ site.url }}/images/stm32dntp_ntpdate.png">

Windows имеет специализированный графический интерфейс для синхронизации времени.

Windows:

<img src="{{ site.url }}/images/stm32dntp_win1.png">

Modbus TCP (Modpoll):
```css
./modpoll -c 10 -r 1 -m tcp 192.168.0.125 
```
<img src="{{ site.url }}/images/stm32dntp_modpoll.png">

# Ссылки:
[Проект на гитхаб](https://github.com/AlexPuts/stm32dntp)

[Проект  программы настройки сервера](https://github.com/AlexPuts/stm32dntpsetuptool)

[Сайт Stm32duino фреймворка](http://stm32duino.com)

[Гитхаб ядра Stm32duino фреймворка](https://github.com/stm32duino/Arduino_Core_STM32)


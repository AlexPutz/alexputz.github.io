---
layout: article
title: "Stm32duino ntp server"
categories: [projects, en]
excerpt: "Ntp time server based on stm32duino/arduino."
ads: false
comments: false
share: true
image:
  teaser: stm32dntp_ide.png
---
<img src="{{ site.url }}/images/stm32dntp_ide.png">

This project features time server based on stm32duino.
- The server is built on stm32duino blue pill, ethernet module enc28j60, gps module ublox.
- The server receives time from gps module or through the setup program by using "Set time" function.
- The server processes and responds on ntp protocol for systems windows(sntp) linux(ntp).
- It includes function for syncronization via Modbus TCP. ( It holds registers with current time on Modbus TCP),this allows to sync time with 1 second precision.

Linux:
```css
sudo ntpdate -d 192.168.0.125
```
<img src="{{ site.url }}/images/stm32dntp_ntpdate.png">

Windows has special gui interface.

Windows:

<img src="{{ site.url }}/images/stm32dntp_win1.png">

Modbus TCP (Modpoll):
```css
./modpoll -c 10 -r 1 -m tcp 192.168.0.125 
```
<img src="{{ site.url }}/images/stm32dntp_modpoll.png">

# Links:
[Project on github](https://github.com/AlexPuts/stm32dntp)

[Server setup tool project](https://github.com/AlexPuts/stm32dntpsetuptool)

[Stm32duino framework site](http://stm32duino.com)

[Core Stm32duino github](https://github.com/stm32duino/Arduino_Core_STM32)


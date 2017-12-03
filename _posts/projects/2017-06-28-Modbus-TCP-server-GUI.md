---
layout: article
title: "Modbus Server GUI"
categories: [projects, en]
excerpt: "QModbusTcpServer based modbus server app (Qt,C++)."
ads: false
share: true
image:
  teaser: mbserver.png
---
<img src="{{ site.url }}/images/mbserver.png">

Modbus server project is built with use of classes <QModbusTcpServer>, <QModbusRtuSerialSlave>. 
This project is based on modbus server example distributed with Qt framework. 
Application interface is composed of server register table and control elements.
Server register table allows user to input register values, control elements enable IP, Port and mode management (TCP/RTU).

<figure>
	<a href="{{ site.url }}/images/modbus_server_diagram.png"><img src="{{ site.url }}/images/modbus_server_diagram.png"></a>
	<figcaption>Project classes diagram.</figcaption>
</figure>

# Links:
[Project on github](https://github.com/AlexPutz/Modbus_server)

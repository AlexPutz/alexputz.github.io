---
layout: article
title: "Modbus Server GUI"
categories: [projects, ru]
excerpt: "Modbus сервер построенный на классе QModbusTcpServer (Qt,C++)."
ads: false
share: true
image:
  teaser: mbserver.png
---
<img src="{{ site.url }}/images/mbserver.png">

Проект Modbus сервера построенный на классе <QModbusTcpServer>, <QModbusRtuSerialSlave>. 
Проект создан на основе примера поставляемого в составе фреймворка Qt. 
Интерфейс программы состоит из поля с таблицей регистров сервера и элементов управления.
Таблица регистров сервера позволяет устанавливать значения регистров, элементы управления позволяют устанавливать IP адрес, 
порт сервера, выбирать режим (TCP/RTU).


<figure>
	<a href="{{ site.url }}/images/modbus_server_diagram.png"><img src="{{ site.url }}/images/modbus_server_diagram.png"></a>
	<figcaption>Диграмма классов проекта.</figcaption>
</figure>

# Ссылки:
[Проект на гитхаб](https://github.com/AlexPutz/Modbus_server)

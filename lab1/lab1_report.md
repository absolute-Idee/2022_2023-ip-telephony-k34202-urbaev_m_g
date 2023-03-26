University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [IP-telephony](https://github.com/itmo-ict-faculty/ip-telephony)  
Year: 2022/2023  
Group: K34202  
Author: Urbaev Maxim Gennadevich  
Lab: Lab1  
Date of create: 08.03.2023  
Date of finished:   

--- 

## Цель работы
Изучить рабочую среду Cisco Packet Tracer, ознакомиться с интерфейсами основных устройств, типами кабелей, научиться собирать топологию. Изучить построение сети IP-телефонии с помощью маршрутизатора, коммутатора и IP телефонов Cisco 7960 в среде Packet tracer

## Ход работы
#### Часть 1

В Cisco Packet Tracer была смоделирована сеть следующей конфигурации

<img src=https://user-images.githubusercontent.com/67152968/227776577-b24eda18-5535-439f-bf9c-83957a3dbb80.png width=500>

В интерфейсах PC каждому был задан IP-aдрес в пределах 192.168.0.1 - 192.168.0.7

<img src=https://user-images.githubusercontent.com/67152968/227776986-6210f35f-69af-487f-bf31-f0f9761a8088.png width=500>

В качестве проверки были пропингованы 4 и 7 компьютеры

<img src=https://user-images.githubusercontent.com/67152968/227777418-4634ac71-984e-4f0f-a89d-b5455b7ce1b7.png width=500>

---

#### Часть 2

Была построена схема 

<img src=https://user-images.githubusercontent.com/67152968/227780330-a098235e-1675-4f6d-bc07-c50510624766.png width=500>

Далее был настроен интерфейс на маршрутизаторе

<img src=https://user-images.githubusercontent.com/67152968/227780519-7ceb3e74-d570-47cf-bbda-c20b5fe2a33f.png width=500>

Был поднят DHCP сервер на маршрутизаторе для IP-телефонов

<img src=https://user-images.githubusercontent.com/67152968/227780668-17937f19-5516-49aa-8f68-cb7df5ef16f7.png width=500>

Теперь нужно дать дополнительную команду для опции 150. Она позволяет подтягивать и автоматически подтягивать прошивки для телефонов с TFTP сервера. Далее настроены VoIP параметры: 
* max-dn - максимально – возможное количество поддерживаемых DN (Directory Numbers). Номеров, другими словами;
* max-ephones - максимальное количество телефонных аппаратов. Сделаем по количеству DN’ов;
* ip source-address - откуда наш роутер будет принимать звонки (запросы) от SCCP девайсов;
* auto assign - присвоение линий в автоматическом режиме;

<img src=https://user-images.githubusercontent.com/67152968/227783700-8c8b8fb0-c9da-48b0-a3c3-4ce4c463e2b4.png width=500>

Нужно включить поддержку VoIP на интерфейсах (голосовой VLAN):

<img src=https://user-images.githubusercontent.com/67152968/227783874-31525e61-65ab-496e-9a2e-4f4a91d0adc6.png width=500>

Далее было включено питание на телефонах

<img src=https://user-images.githubusercontent.com/67152968/227784040-a51b0a64-d7a1-4bef-be95-f68cf0ffa078.png width=500>

В консоли маршрутизатора присвоим телефонные номера.

<img src=https://user-images.githubusercontent.com/67152968/227784266-f3288a86-806b-471d-8870-25ce89d6f2db.png width=500>

Проверка звонка

<img src=https://user-images.githubusercontent.com/67152968/227784445-9510f595-199c-4e95-b05f-bec33bc26669.png width=500>

## Вывод

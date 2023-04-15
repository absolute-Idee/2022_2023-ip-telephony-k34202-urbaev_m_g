University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [IP-telephony](https://github.com/itmo-ict-faculty/ip-telephony)  
Year: 2022/2023  
Group: K34202  
Author: Urbaev Maxim Gennadevich  
Lab: Lab1  
Date of create: 26.03.2023  
Date of finished:   

--- 

## Цель работы
Изучить построение сети IP-телефонии с помощью маршрутизатора Cisco 2811, коммутатора Cisco catalyst 3560 и IP телефонов Cisco 7960.

## Ход работы
#### Часть 1

Была смоделирована сеть:  
<img src=https://user-images.githubusercontent.com/67152968/227789498-546dfccc-db8b-4322-8c81-50d645fe5016.png width=500>

Были заданы пароли для защиты маршрутизатора как в удаленном режиме, так и в режиме консоли:

<img src=https://user-images.githubusercontent.com/67152968/227789984-6b7d94ac-f532-4505-9f47-2bbdcbc0d1e3.png width=500>

Далее был сконфигурирован интерфейс fa0/0

<img src=https://user-images.githubusercontent.com/67152968/227790209-f0949000-bf7c-4dfa-b748-8d7cf9ceac37.png width=500>

Для автоматической настройки компьютеров и IP-телефонов в сети надо настроить DHCP сервер на маршрутизаторе Cisco 2811. В конфигурационном режиме был создан пул DHCP адреса с названием VOICE:

<img src=https://user-images.githubusercontent.com/67152968/227790693-0a42a5a6-164e-4b20-86b2-df54b49603a1.png width=500>

После проделанных настроек необходимо заняться настройкой CallManager Express, то есть телефонного сервиса в автоматическом режиме. В данном режиме ведется диалоговый обмен сообщениями, маршрутизатор только запрашивает необходимые параметры. Были заданы максимальное количество номеров, максимальное количество телефонов. Также указан адрес голосового шлюза, а также автоматическое назначение номеров

<img src=https://user-images.githubusercontent.com/67152968/227791234-9d5d9aba-3033-493f-9c49-2d8e3cc98a3f.png width=500>

Был настроен интерфейс управления коммутатором в сети VLAN через назначение диапазона портов

<img src=https://user-images.githubusercontent.com/67152968/227791482-2ac4b959-7370-4324-8a54-2691f6fa0a78.png width=500>

Для возможности дальнейшего общения необходимо дополнительная конфигурация. Для этого создаем первую логическую «телефонную» линию (directory number). Каждому телефону можно определить
несколько таких логический линий со своими номерами:

<img src=https://user-images.githubusercontent.com/67152968/227792103-236be0f4-37cd-4d8e-9584-aced26c170e6.png width=500>

Прозвон телефонов:

<img src=https://user-images.githubusercontent.com/67152968/231814928-3937ca87-a722-409b-a19a-3480962e872b.png width=700>


#### Часть 2

Была построена сеть: 
<img src=https://user-images.githubusercontent.com/67152968/232232275-f3ce2c17-b6f6-4cd6-825d-3c2dd78d57f5.png width=700>

На коммутаторе были созданы VLAN Date, Voice, Management

<img src=https://user-images.githubusercontent.com/67152968/232205773-12e4a17c-9800-4108-8ede-10552f3961fb.png width=500>

Далее настроим vlan 99 и зададим маршрут по умолчанию. Настроим интерфейс управления коммутатором в сети VLAN через
назначение диапазона портов:

<img src=https://user-images.githubusercontent.com/67152968/232205823-2cca7cdd-b561-46fd-beac-370e7b7ac084.png width=500>

Включаем интерфейс FastEthernet0/0 и создаем логический подынтерфейса для VLAN 10, VLAN 20, VLAN 99: 

<img src=https://user-images.githubusercontent.com/67152968/232206167-fb8698dc-3d05-4a06-a38e-ddf38cf99ce3.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206182-679a6635-1e1b-4c9a-ba3a-632bcb0b476a.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206194-843c855b-aced-4263-b667-dcfb7ad34da8.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206393-2e236422-f24e-48d3-9d03-0078e5efbf9a.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206565-68f437ca-6ccd-494e-9ff8-2825e304b10c.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206702-58d678ff-38ad-4eed-9ee2-0d1cc9bc8f8c.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232206831-5a33e2b2-1d2c-4d24-a01f-76e6320a5e84.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232207351-c700eb41-b155-4535-9174-f0b0d4e94c62.png width=500>





## Вывод
В результате выполнения работы был освоен базовый функционал Cisco Packet Tracer, а также смоделирована сеть IP-телефонии

University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [IP-telephony](https://github.com/itmo-ict-faculty/ip-telephony)  
Year: 2022/2023  
Group: K34202  
Author: Urbaev Maxim Gennadevich  
Lab: Lab1  
Date of create: 15.04.2023  
Date of finished:   

--- 

## Цель работы
Изучить построение сети IP-телефонии между удаленными филиалами с помощью маршрутизаторов Cisco 2811 и коммутаторов Cisco 2950Т.Изучить построение сети IP-телефонии между удаленными филиалами с помощью маршрутизаторов Cisco 2811 и Cisco 2600XM.

## Ход работы

Между маршрутизаторами должно быть проложено DCE/DTE соединение. Для этого на роутерах были добавлены новые разъемы при выключенном питании:  
<img src=https://user-images.githubusercontent.com/67152968/232216710-1977d94c-9d11-46a4-b5e0-feb5c82a849b.png width=500>

Перед выполнением необходимых настроек, необходимо настроить оконченные устройства сети на DHCP:  
<img src=https://user-images.githubusercontent.com/67152968/232210471-5ea221a6-6e41-4dee-8940-a315f615c544.png width=500>

Далее были настроены конфигурации интерфейсов fa0/0 на маршрутизаторах RouterA и RouterB:  

<img src=https://user-images.githubusercontent.com/67152968/232210593-c376023f-4482-46bd-ad04-5bbaf6a481f9.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232210695-554ba1ee-1abd-4c5f-a2e5-76ba7fc66d02.png width=500>

Также были сконфигурированы интерфейсы s1/0 на роутерах. На роутере А был настроен DCE порт, на роутере B DTE порт:

<img src=https://user-images.githubusercontent.com/67152968/232218457-7b8a1672-30a9-49f1-896f-35fe7b5fd3dd.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232219591-f85923df-3884-4e9c-8bd8-1d190b6b9578.png width=500>

В результате была настроена сеть:

<img src=https://user-images.githubusercontent.com/67152968/232219774-78c6c511-78c7-4f3c-b2df-f054ac8b878b.png width=800>

Для автоматической настройки компьютеров и IP-телефонов в сети надо настроить DHCP сервер на маршрутизаторе Cisco 2811. В конфигурационном режиме был создан пул DHCP адреса с названием Т1 и T2. Также была настроена динамическая маршрутизации на основе протокола RIP второй версии для передачи информации между маршрутизаторами в сети:

<img src=https://user-images.githubusercontent.com/67152968/232221023-d9a4f4b0-cfd2-4c3f-b01e-cb844a739060.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232222035-ade14419-37c5-4ed4-8904-2d754333b7a4.png width=500>

После проделанных настроек необходимо заняться настройкой CallManager Express, то есть телефонного сервиса в автоматическом режиме. В данном режиме ведется диалоговый обмен сообщениями, маршрутизатор только запрашивает необходимые параметры. Для включения
данного сервиса в конфигурационном режиме набираем следующие команды. Также были заданы максимальное количество номеров, максимальное количество телефонов.

<img src=https://user-images.githubusercontent.com/67152968/232222704-bd910934-e872-4774-9307-cea8e2b6052a.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232223045-bb20f9fd-07ea-42c3-ae83-c69463ec8f79.png width=500>

На коммутаторах назначим диапазон портов:

<img src=https://user-images.githubusercontent.com/67152968/232223157-54382382-0666-4250-8148-8e61904b2f79.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232223262-e8bd700d-8a2e-48f4-a21b-06ec8cf99565.png width=500>

Для возможности дальнейшего общения необходимо дополнительная конфигурация. Для этого создаем первую логическую «телефонную» линию (directory number). Каждому телефону нужно определить несколько таких логический линий со своими номерами:

<img src=https://user-images.githubusercontent.com/67152968/232224704-70a39eda-c643-41f5-81a8-9b61d67e93d7.png width=500>

<img src=https://user-images.githubusercontent.com/67152968/232224751-4f07a8aa-b257-4173-ad1f-716b94128a13.png width=500>

Результат пинга между компьютерами:

<img src=https://user-images.githubusercontent.com/67152968/232224649-8979163e-194d-4a49-b8b8-adb301bad30f.png width=500>

Результат прозвона телефонов:

<img src=https://user-images.githubusercontent.com/67152968/232224813-3d3dad88-f909-4dda-8b89-a5758e66ecf6.png width=500>

## Вывод
В ходе выполнения лабораторной работы был изучен алгоритм построения сети IP-телефонии между удаленными филиалами с помощью маршрутизаторов Cisco  2811 и коммутаторов Cisco 2950T.

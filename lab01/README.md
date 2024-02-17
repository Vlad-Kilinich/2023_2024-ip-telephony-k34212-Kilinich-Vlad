University: [ITMO University](https://itmo.ru/ru/) <br/>
Faculty: [FICT](https://fict.itmo.ru) <br/>
Course: IP-telephony <br/>
Year: 20232/2024 <br/>
Group: K34202 <br/>
Author: Kilinich Vladislav <br/>
Lab: Lab1 <br/>
Date of create: 18.02.2024 <br/>
Date of finished: - <br/>

# Лабораторная работа №1 "Базовая настройка ip-телефонов в среде Сisco packet tracer"  

## Цель работы:  
   Изучить рабочую среду Cisco Packet Tracer, ознакомить- ся с интерфейсами основных устройств, типами кабелей, научиться собирать топологию. Изучить построение сети IP-телефонии с помощью маршрутизатора, коммутатора и IP телефонов Cisco 7960 в среде Packet tracer

## Ход работы:  
## Часть 1.  
   Первым делом была построена топология сети, которая включает компьютеры, коммутаторы.
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_5_2024-02-18_01-06-24.jpg?raw=true" width="600" heidth = '500'>  
</p> 

   Каждому компьютеру были назначены статитические IP-адреса 192.168.10.1-192.168.10.7/24.
   Далее проверяем доступность каждого узла.  
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_1_2024-02-18_01-40-25.jpg?raw=true" width="300" heidth = '500'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_4_2024-02-18_01-06-24.jpg?raw=true" width="300" heidth = '500'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_2_2024-02-18_01-06-24.jpg?raw=true" width="390" heidth = '500'> 
</p>  

## Часть 2.  
   Была простроена следующая топология.  
   
   <p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_9_2024-02-18_01-06-24.jpg?raw=true" width="500" heidth = '300'> 
   </p>
   
   На маршрутизаторе были настроены интерфейс Fa0/0, DHCP-сервер и услуги телефонии, все команды приведены на скринах ниже.
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_8_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_12_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_6_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_10_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_13_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
</p> 
  
   Далее настроиваем vlan на коммутаторе.
   
   <p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_14_2024-02-18_01-06-24.jpg?raw=true" width="400" heidth = '250'> 
   </p>

   Далее подключаем телефоны к питанию и пытаемся дозвониться друг другу.
   
   <p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_11_2024-02-18_01-06-24.jpg?raw=true"> 
   </p>
  
   
   
## Выводы: ##
Таким образом, была построена топология сети, назначены IP-адреса, была настроена телефония.

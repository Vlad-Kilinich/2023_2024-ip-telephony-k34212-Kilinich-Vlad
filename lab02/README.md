University: [ITMO University](https://itmo.ru/ru/) <br/>
Faculty: [FICT](https://fict.itmo.ru) <br/>
Course: IP-telephony <br/>
Year: 2023/2024 <br/>
Group: K34202 <br/>
Author: Kilinich Vladislav <br/>
Lab: Lab2 <br/>
Date of create: 24.02.2024 <br/>
Date of finished: - <br/>

# Лабораторная работа №2 "Конфигурация voip в среде Сisco packet tracer"  

## Цель работы:  
  Изучить построение сети IP-телефонии с помощью маршрутизатора Cisco 2811, коммутатора Cisco catalyst 3560 и IP телефонов Cisco 7960.

## Ход работы:  
## Часть 1.  
   Первым делом была построена топология сети, которая включает компьютеры, коммутаторы и маршрутизатор.
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/1%20часть.jpg?raw=true" width="600" heidth = '500'>  
</p> 

1) Далее В было изменено название маршрутизатора на "CMERouter" командой ```hostname```  
2) Отключаем синтаксис ввода слов от DNS серверов командой ```no ip domain-lookup```.  
3) Задайем пароли для защиты маршрутизатора как в удаленном режиме, так и в режиме консоли:  
```  
line vty 0 4
password 123
login
lie console 0
password 123
login
```  
4) Настроем интерфейс fa0/0 на маршрутизаторе CMERouter:  
```  
interface fa0/0
ip address 192.168.0.1 255.255.255.0
no shutdown
```  
5) Настроим DHCP сервер для передачи голоса и данных на маршрутизаторе + пишем "option 150 ip 192.168.0.1" для работы IP-телефонии:
```
ip dhcp pool voice
network 192.168.0.0 255.255.255.0
default-router 192.168.0.1
option 150 ip 192.168.0.1
```  
6) Настроим услуги телефонии Cisco CallManager Express на маршрутизаторе:
```
telephony-service
max-dn 10
max-ephones 10
ip source-address 192.168.0.1 port 3100
auto assign 1 to 19
```
7) Создаем VLAN порты на коммутаторе для взаимодействия коммутатора с маршрутизатором и подключаем IP телефоны.

```
telephony-service
max-dn 10
max-ephones 10
ip source-address 192.168.0.1 port 3100
auto assign 1 to 19
```
8) Настройка vlan на коммутаторе:
```
nterface range fa0/1-4
switchport mode access
switchport voice vlan 1
```
9) Даем номера телефонам на роутере и проверяем работоспособность: 

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_2_2024-02-24_15-08-40.jpg?raw=true" width="500" heidth = '400'> 
</p>  
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/1.jpg?raw=true" width="800" heidth = '550'> 
</p>  

## Часть 2.  
1) Была простроена следующая топология.  
   
  

   Далее подключаем телефоны к питанию и пытаемся дозвониться друг другу.
   
   <p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_11_2024-02-18_01-06-24.jpg?raw=true"> 
   </p>
  
   
   
## Выводы: ##
В ходе лабораторной работы была построена топология сети, назначены IP-адреса и настроена IP-телефония.

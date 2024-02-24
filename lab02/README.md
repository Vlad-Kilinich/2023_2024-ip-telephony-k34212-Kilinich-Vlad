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
Была простроена следующая топология.  
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_5_2024-02-24_14-40-21.jpg?raw=true" width="600" heidth = '500'> 
</p> 
1) Создаем VLAN порты на коммутаторе для взаимо-действия коммутатора с маршрутизатором и подключаем IP телефоны.  

```
vlan 10
name data
vlan 20
name voice
vlan 30
name router
```
2) Интерфейсы для телефонов переведены в режим access и подключены к VLANам для телефонов и компьютеров командами:
```
interface range fa0/2-4
switchport mode access
switchport access vlan 10
switchport voice vlan 20
```
А интерфейс к роутеру был переведен в режим trunk и настраиваем VLAN. Также был задан маршрут по умолчанию на сеть 192.168.2.0
```
interface vlan 30
ip address 192.168.2.1 255.255.255.0
no shutdown
interface fa0/1
switchport mode trunk
switchport trunk native vlan 30
exit
ip default-network 192.168.2.0 
```
3) Создаем саб-интерфейсы для каждого vlan:
```
interface FastEthernet0/0.10
encapsulation dot1Q 10
ip add 192.168.10.10 255.255.255.0
no shutdown
interface FastEthernet0/0.120
encapsulation dot1Q 20
ip add 192.168.20.10 255.255.255.0
no shutdown
interface FastEthernet0/0.30
encapsulation dot1Q 30
ip add 192.168.30.10 255.255.255.0
no shutdown
```
4) Настраиваем DHCP для передачи голоса и данных командами:
```
ip dhcp excluded-address 192.168.10.10
ip dhcp excluded-address 192.168.20.10
ip dhcp pool data
network 192.168.10.0 255.255.255.0
default-router 192.168.10.10
exit
ip dhcp pool voice
network 192.168.20.0 255.255.255.0
default-router 192.168.20.10
option 150 ip 192.168.20.10
```  
5) После этого подключаем телефоны и создаем сервис ip-телефонии.
```
telephony-service
max-dn 3
max-ephones 3
ip source-address 192.168.20.10 port 2000
```  
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_3_2024-02-24_14-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>   
6) Проверяем пинги на телефоны:  
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_2_2024-02-24_14-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_1_2024-02-24_14-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>  
7) Проверяем пинги на компьютеры:
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab02/images/photo_4_2024-02-24_14-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>  

## Выводы: ##
В ходе лабораторной работы были построены схемы сети IP-телефонии и настроены устройства, в результате чего успешно установили связь между IP-телефонами в первой части. Во второй части – еще и между компьютерами.

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
   Первым делом была построена топология сети, которая включает компьютеры, коммутаторы.
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_5_2024-02-18_01-06-24.jpg?raw=true" width="800" heidth = '700'>  
</p> 

   Каждому компьютеру были назначены статитические IP-адреса 192.168.10.1-192.168.10.7/24.
   Далее проверяем доступность каждого узла.
   
<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_1_2024-02-18_01-40-25.jpg?raw=true" width="350" heidth = '500'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_4_2024-02-18_01-06-24.jpg?raw=true" width="350" heidth = '500'> 
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab01/images/photo_2_2024-02-18_01-06-24.jpg?raw=true" width="350" heidth = '500'> 
</p> 
   
   Была простроена следующая топология.
   
   [<img src="https://user-images.githubusercontent.com/58363643/222966714-38d13b4c-c0b9-4da8-9e9c-d740e25e8b67.png" width="300"/>](https://user-images.githubusercontent.com/58363643/222966714-38d13b4c-c0b9-4da8-9e9c-d740e25e8b67.png)
   
   На маршрутизаторе настроен интерфейс Fa0/1, настроен DHCP-сервер, настроены услуги телефонии.
   
   [<img src="https://user-images.githubusercontent.com/58363643/222966835-c350a0c6-3b74-479b-8b38-199305d3ada1.png" width="400"/>](https://user-images.githubusercontent.com/58363643/222966835-c350a0c6-3b74-479b-8b38-199305d3ada1.png)
   [<img src="https://user-images.githubusercontent.com/58363643/222966848-7d30115b-2094-48f4-aad2-2da3d22cf4a0.png" width="400"/>](https://user-images.githubusercontent.com/58363643/222966848-7d30115b-2094-48f4-aad2-2da3d22cf4a0.png)
  
   Настроен vlan на коммутаторе.
   
   [<img src="https://user-images.githubusercontent.com/58363643/222966960-d5205933-d7d4-4b0d-ae65-3381abc971b7.png" width="400"/>](https://user-images.githubusercontent.com/58363643/222966960-d5205933-d7d4-4b0d-ae65-3381abc971b7.png)

   Каждому телефону был назначен номер. Далее проверена работа, настроенной телефонии.
   
   [<img src="https://user-images.githubusercontent.com/58363643/222967133-10045e42-caec-4f85-b907-71cb8e6e7011.png" width="100"/>](https://user-images.githubusercontent.com/58363643/222967133-10045e42-caec-4f85-b907-71cb8e6e7011.png)
  
  [<img src="https://user-images.githubusercontent.com/58363643/222967148-97f3da8a-00b8-4ce8-b66c-9dfb68ac7e4d.png" width="400"/>](https://user-images.githubusercontent.com/58363643/222967148-97f3da8a-00b8-4ce8-b66c-9dfb68ac7e4d.png)

   
   
## Выводы: ##
Таким образом, была построена топология сети, назначены IP-адреса, была настроена телефония.

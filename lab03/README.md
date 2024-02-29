University: [ITMO University](https://itmo.ru/ru/) <br/>
Faculty: [FICT](https://fict.itmo.ru) <br/>
Course: IP-telephony <br/>
Year: 2023/2024 <br/>
Group: K34212 <br/>
Author: Kilinich Vladislav <br/>
Lab: Lab3 <br/>
Date of create: 29.02.2024 <br/>
Date of finished: - <br/>

# Лабораторная работа №3 "Использование Asterisk в качестве SIP proxy"  

## Цель работы:  
  Изучить программный комплекс Asterisk. Настройка Asterisk для локальных звонков.

## Ход работы:    
Первым делом устанавливаем Asterisk: ```sudo apt-get install asterisk```.
   
После этого выбираем soft phone
1) Zoiper
2) MicroSIP (понадобилось установить и настроить Wine)

Далее настроим файлы asterisk. Первый файл sip.conf:  

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab03/images/photo_2_2024-02-29_23-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>   

И файл extensions.conf:  

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab03/images/photo_3_2024-02-29_23-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>  

Осталось только настроить телефоны:  

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab03/images/photo_5_2024-02-29_23-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>

Запускаем сервис Asterisk: ```sudo service asterisk start```

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab03/images/photo_4_2024-02-29_23-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>

И теперь проверяем связанность телефонов:  

<p align="center">
<img src="https://github.com/Vlad-Kilinich/2023_2024-ip-telephony-k34212-Kilinich-Vlad/blob/main/lab03/images/photo_1_2024-02-29_23-40-21.jpg?raw=true" width="500" heidth = '400'> 
</p>

## Выводы: ##
В ходе лабораторной работы успешно настроен сервис Asterisk и установлена связь между телефонами MicroSIP и Zoiper.  

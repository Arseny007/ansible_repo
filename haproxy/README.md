# 5 Лабораторная работя
## Ansible + Haproxy + Keepalived

> Задание:

 + На серверах web1, web2 установить Nginx.
 + На серверах haproxy1, haproxy2 установить и настроить  отказоустойчивую связку HAProxy+Keepalived. Настроить VIP с помощью Keepalived в соответствии со схемой
 + На серверах web1, web2 Nginx должен работать по порту 8080 и отдавать кастомную страницу, зайдя на которую можно понять на каком сервере вы находитесь.
 + На серверах с HAProxy ПО должно обеспечить балансировку нагрузки серверов web1 и web2 в режиме round-robin. Сделать таймауты ожидания ответа web1 и web2 как можно меньше. Скажем, 1-2 секунды
 + Установка и настройка всего ПО должна быть обеспечена Ansible-сценарием.
 + Все файлы по этому заданию выложить в Github и написать ReadMe со скринами работоспособности и инструкцию по запуску вашего Ansible-сценария.
 
## Как выполнить задание?
 + Клонировать репозиторий 
 + `git clone https://github.com/Arseny007/ansible_repo.git`
 + В терминале открыть папку balansir `cd haproxy`
 + Открываем [Vagrantfile](https://github.com/Arseny007/ansible_repo/blob/master/haproxy/Vagrantfile)
 + меняем 46ую строчку `ssh_pub_key = File.readlines("/home/arseny/.ssh/id_rsa.pub").first.strip`
 + +  надо указать тут свой путь до ключа
 + чтобы поднять виртуальные системы, вводим в консоль `vagrant up`
 + чтобы установить весь софт, вводми в консоль`ansible-playbook nginx.yml`

## Для тех, кому лень:
 + **1)** Для начала оставим одну виртуальную машину с haproxy, она должна балансировать на web1 и web2:
 + ![вот так](https://github.com/Arseny007/ansible_repo/blob/master/pictures/haproxy/Screenshot%20from%202022-04-05%2013-26-42.png)
 + ![и вот так](https://github.com/Arseny007/ansible_repo/blob/master/pictures/haproxy/Screenshot%20from%202022-04-05%2013-27-08.png)
 + **2)** Затем поднимаем вторую виртуалку с haproxy, ждем и выключаем виртуалку, которая была включена в 1 пункте:
 + ![так](https://github.com/Arseny007/ansible_repo/blob/master/pictures/haproxy/Screenshot%20from%202022-04-05%2013-30-20.png)
 + ![и так](https://github.com/Arseny007/ansible_repo/blob/master/pictures/haproxy/Screenshot%20from%202022-04-05%2013-30-34.png)

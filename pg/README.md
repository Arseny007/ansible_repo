# 6 Лабораторная работя
## Postgresql + Replication + Wal arcvive ( + Ansible optional)

> Задание:

 + На сервера pg1 и pg2 установить PostgreSQL. 
 + Репликация данных 
 + Архивирование WAL
 
## Как выполнить задание?
 + Клонировать репозиторий 
 + `git clone https://github.com/Arseny007/ansible_repo.git`
 + В терминале открыть папку pg `cd pg`
 + Открываем [Vagrantfile](https://github.com/Arseny007/ansible_repo/blob/master/haproxy/Vagrantfile)
 + меняем 46ую строчку `ssh_pub_key = File.readlines("/home/arseny/.ssh/id_rsa.pub").first.strip`
 + +  надо указать тут свой путь до ключа
 + чтобы поднять виртуальные системы, вводим в консоль `vagrant up`
 + чтобы установить весь софт, вводми в консоль`ansible-playbook postgres.yml`

## Для тех, кому лень:
 + **1)** Таблицы перенеслись с мастера. На реплике пытаемся создать табличку, выводит ошибку, мол, read-only:
 + ![1](https://github.com/Arseny007/ansible_repo/blob/master/pictures/pg/Screenshot%20from%202022-04-09%2014-05-46.png)
 + **2)** wal в архиве /wal:
 + ![2](https://github.com/Arseny007/ansible_repo/blob/master/pictures/pg/Screenshot%20from%202022-04-09%2014-05-46.png)

# 7 Лабораторная работя
## Patroni + Consul

> Задание:

 + **1)** Настроить консул ( использовать уже готовую роль и инветори).
 + **2)** База данных должна быть проинициализирована на выделенных дисках (в Vargrantfile они уже подключены). БД должна находить в папке /pgsql/pg_data/14. WAL архивы должны находить в папке /pgsql/pg_wal/14. В эти папки должны быть примонтированы диски /dev/sdb и /dev/sdc соответственно. Диски должны быть подключены в LVM и отформатированы в файловой системе xfs.
 + **3)** На серверах pg1 и pg2 настроить оркестратор репликации Patroni (пакет в архиве).
 + **4)** С помощью утилиты vip-manager обеспечить настройку VIP адреса на мастер сервере. https://github.com/cybertec-postgresql/vip-manager/releases/download/v1.0.2/vip-manager-1.0.2-1.x86_64.rpm . Напоминаю, что в конфиге vip-manager необходимо настроить подключение по DCS Consul. IP адрес подключения 127.0.0.1:8500. Так же нужно будет указать consul_token, переменную которого можно взять в роли consul
 
## Как выполнить задание?
 + Клонировать репозиторий 
 + `git clone https://github.com/Arseny007/ansible_repo.git`
 + В терминале открыть папку pg `cd patroni/ +/ consul`
 + Открываем [Vagrantfile](https://github.com/Arseny007/ansible_repo/blob/master/patroni%20%2B%20consul/Vagrantfile)
 + меняем 46ую строчку `ssh_pub_key = File.readlines("/home/arseny/.ssh/id_rsa.pub").first.strip`
 + +  надо указать тут свой путь до ключа
 + Для корректной работы необходим собранный образ norma
 + чтобы поднять виртуальные системы, вводим в консоль `vagrant up`
 + чтобы установить весь софт, вводми в консоль`ansible-playbook work.yml`

## Для тех, кому лень:
 + **1)** Slave в режиме Sync Standby:
 + ![1](https://github.com/Arseny007/ansible_repo/blob/master/pictures/patroni/Screenshot%20from%202022-04-15%2014-48-14.png)

# Домашнее задание №1



# Задания

#### 1. Узнать IP-адрес интерфейса, подключенного к сети Интернет
```sh
[root@dev-server ~] ip addr show | grep 'inet ' | grep -v 127.0.0.1
inet 93.183.72.60/24 brd 93.183.72.255 scope global noprefixroute enp0s5
```

#### 2. Создать именованный пайп (named pipe). Вывести в файл через созданный pipe вывод команды `ss -plnt`
```sh
[root@dev-server ~] mkfifo trully_pipe
[root@dev-server ~] ss -plnt > trully_pipe &
[1] 19477
[root@dev-server ~] cat trully_pipe > output.txt
[1]+  Done                    ss -plnt > trully_pipe
```
#### 3. При помощи именованного пайпа заархивировать всё, что в него отправляем. Например, содержимое файла `/var/log/messages`. На выходе получить архив tar или любой другой
```sh
[root@dev-server ~]# mkfifo /tmp/archive_pipe
[root@dev-server ~]# tar czf /tmp/messages_archive.tar.gz -C /var/log messages < /tmp/archive_pipe &
[root@dev-server ~]# echo "/var/log/messages" > /tmp/archive_pipe
```
#### 4. Вывести дату в unixtime. На вход команды `date` через пайп подать свой формат выводимой даты
```sh
[root@dev-server ~] echo "2024-01-01 00:00:00 UTC" | date -f - +%s
```
#### 5. При помощи HEREDOC записать в файл многострочное сообщение
```sh
[root@dev-server ~] cat <<EOF > message.txt
DevOps 1
DevOps 2
DevOps 3
DevOps 4
DevOps 5
EOF
```



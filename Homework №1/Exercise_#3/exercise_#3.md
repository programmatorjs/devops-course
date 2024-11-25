#### 3. При помощи именованного пайпа заархивировать всё, что в него отправляем. Например, содержимое файла `/var/log/messages`. 
На выходе получить архив tar или любой другой
```sh
[root@dev-server ~]# mkfifo /tmp/archive_pipe
[root@dev-server ~]# tar czf /tmp/messages_archive.tar.gz -C /var/log messages < /tmp/archive_pipe &
[root@dev-server ~]# echo "/var/log/messages" > /tmp/archive_pipe
```

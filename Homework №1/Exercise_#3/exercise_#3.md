#### 3. При помощи именованного пайпа заархивировать всё, что в него отправляем. Например, содержимое файла `/var/log/messages`. 
На выходе получить архив tar или любой другой
```sh
[root@dev-server ~]# mkfifo /tmp/archive_pipe
[root@dev-server ~]# tar czf /tmp/messages_archive.tar.gz -C /var/log messages < /tmp/archive_pipe
[root@dev-server ~]# cat /var/log/messages > /tmp/archive_pipe
[root@dev-server ~]# cd /tmp
[root@dev-server tmp]# ls
archive_pipe             my_fifo
messages_archive.tar.gz  systemd-private-a1bed2f5d5c845f5acb26392f249b8b5-chronyd.service-zujjAG
```
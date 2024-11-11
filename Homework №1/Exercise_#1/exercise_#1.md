#### 1. Узнать IP-адрес интерфейса, подключенного к сети Интернет
```sh
[root@dev-server ~] ip addr show | grep 'inet ' | grep -v 127.0.0.1
inet 93.183.72.60/24 brd 93.183.72.255 scope global noprefixroute enp0s5
```
### Установка LXC:
```sh
apt-get install lxc
```
![](1a.png)
![](1b.png)
### Создание и настройка контейнера:
```sh
lxc-create -n mycontainer -t download -- -d ubuntu -r focal -a amd64
lxc-start -n mycontainer
```
![](2a.png)
### Автозапуск контейнера и ограничение памяти:
```sh
nano /var/lib/lxc/mycontainer/config
lxc.cgroup2.memory.max = 256M
lxc.start.auto = 1
```
![](3a.png)
![](3b.png)
### Перезагрузка и анализ логов: 
```
lxc-start -n mycontainer --logfile log.log
lxc-attach -n mycontainer
free -m
```
![](4a.png)
![](5a.png)

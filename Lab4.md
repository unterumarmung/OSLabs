# Лабораторная работа № 4
## Знакомство с демонами (юнитами) Linux

### Часть 1

```
daniil@vstu:~$ sudo so
[sudo] password for daniil: 
sudo: so: command not found
daniil@vstu:~$ sudo su
root@vstu:/home/daniil# cd /etc/systemd/system
root@vstu:/etc/systemd/system# touch sleep.service
root@vstu:/etc/systemd/system# vim sleep.service
```
![image](https://user-images.githubusercontent.com/39276703/165708234-670a0e3d-cb03-4d70-b672-80127267b470.png)
```
root@vstu:/etc/systemd/system# systemctl daemon-reload
root@vstu:/etc/systemd/system# systemctl start sleep.service
```
```
root@vstu:/etc/systemd/system# systemctl status sleep.service
● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; disabled; vendor p>
     Active: active (running) since Thu 2022-04-28 11:15:15 +03; 23s ago
   Main PID: 1761 (sleep)
      Tasks: 1 (limit: 4575)
     Memory: 196.0K
     CGroup: /system.slice/sleep.service
             └─1761 /bin/sleep 90

апр 28 11:15:15 vstu systemd[1]: Started Sleeping.
lines 1-10/10 (END)
```
```
root@vstu:/etc/systemd/system# watch systemctl status sleep.service
Every 2,0s: systemctl status sleep.service   vstu: Thu Apr 28 11:17:05 2022

● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; disabled; vendor pr
eset: enabled)
     Active: inactive (dead)

апр 28 11:16:47 vstu systemd[1]: /etc/systemd/system/sleep.service:8: Faile
d to parse service restart specifier, ignoring: none
```

### Часть 2

![image](https://user-images.githubusercontent.com/39276703/165709265-662ca0c9-5cad-44d3-9f33-7b6572fa4575.png)

```
root@vstu:/etc/systemd/system# systemctl daemon-reload
root@vstu:/etc/systemd/system# systemctl start sleep.service
root@vstu:/etc/systemd/system# systemctl status sleep.service
● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; disabled; vendor p>
     Active: active (running) since Thu 2022-04-28 11:20:00 +03; 6s ago
   Main PID: 1926 (sleep)
      Tasks: 1 (limit: 4575)
     Memory: 168.0K
     CGroup: /system.slice/sleep.service
             └─1926 /bin/sleep 90

апр 28 11:20:00 vstu systemd[1]: Started Sleeping.
lines 1-10/10 (END)
```

### Часть 3

```
root@vstu:/etc/systemd/system# systemctl enable sleep.service
Created symlink /etc/systemd/system/multi-user.target.wants/sleep.service → /etc/systemd/system/sleep.service.
root@vstu:/etc/systemd/system# reboot now
```
```
daniil@vstu:~$ sudo su
[sudo] password for daniil: 
root@vstu:/home/daniil# systemctl status sleep.service
● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; enabled; vendor preset>
     Active: active (running) since Thu 2022-04-28 11:22:23 +03; 1min 4s ago
   Main PID: 590 (sleep)
      Tasks: 1 (limit: 4575)
     Memory: 204.0K
     CGroup: /system.slice/sleep.service
             └─590 /bin/sleep 90

апр 28 11:22:23 vstu systemd[1]: Started Sleeping.
lines 1-10/10 (END)
```

### Часть 4

```
root@vstu:/home/daniil# cd /etc/systemd/system/
root@vstu:/etc/systemd/system# touch terminal.service
root@vstu:/etc/systemd/system# vim terminal.service 
```

![image](https://user-images.githubusercontent.com/39276703/165710849-e9c7418f-57ee-4918-a631-112b08a954e8.png)
```
root@vstu:/etc/systemd/system# systemctl daemon-reload
root@vstu:/etc/systemd/system# systemctl start terminal.service
root@vstu:/etc/systemd/system# systemctl status terminal.service
```
![image](https://user-images.githubusercontent.com/39276703/165713244-ef86dc3f-3a3f-4df4-a1f3-40988ac8d447.png)

### Часть 5

```
root@vstu:/home/daniil# systemctl enable terminal.service
Created symlink /etc/systemd/system/graphical.target.wants/terminal.service → /etc/systemd/system/terminal.service.
root@vstu:/home/daniil# reboot now
```

![image](https://user-images.githubusercontent.com/39276703/165713990-45c1382e-168f-4d8f-8c4e-79864cafdfa6.png)


```
daniil@vstu:/$ sudo su
[sudo] password for daniil: 
root@vstu:/# systemctl status sleep.service
● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; enabled; vendor preset>
     Active: active (running) since Thu 2022-04-28 11:43:37 +03; 1min 13s ago
   Main PID: 588 (sleep)
      Tasks: 1 (limit: 4575)
     Memory: 200.0K
     CGroup: /system.slice/sleep.service
             └─588 /bin/sleep 90

апр 28 11:43:37 vstu systemd[1]: Started Sleeping.
root@vstu:/# systemctl disable terminal.service
Removed /etc/systemd/system/graphical.target.wants/terminal.service.
root@vstu:/# # systemctl stop terminal.service
root@vstu:/# systemctl status sleep.service
● sleep.service - Sleeping
     Loaded: loaded (/etc/systemd/system/sleep.service; enabled; vendor preset>
     Active: active (running) since Thu 2022-04-28 11:45:09 +03; 8s ago
   Main PID: 1653 (sleep)
      Tasks: 1 (limit: 4575)
     Memory: 164.0K
     CGroup: /system.slice/sleep.service
             └─1653 /bin/sleep 90

апр 28 11:45:09 vstu systemd[1]: sleep.service: Scheduled restart job, restart>
апр 28 11:45:09 vstu systemd[1]: Stopped Sleeping.
апр 28 11:45:09 vstu systemd[1]: Started Sleeping.
root@vstu:/# systemctl stop sleep.service
root@vstu:/# systemctl disable sleep.service
Removed /etc/systemd/system/multi-user.target.wants/sleep.service.
```

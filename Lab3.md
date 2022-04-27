# Лабораторная работа №3
## Пользователи и права доступа в Linux
### Часть 1

```
daniil@vstu:~$ sudo su
[sudo] password for daniil: 

root@vstu:/home/daniil# adduser master
Adding user `master' ...
Adding new group `master' (1001) ...
Adding new user `master' (1001) with group `master' ...
Creating home directory `/home/master' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for master
Enter the new value, or press ENTER for the default
	Full Name []: Elon Musk        
	Room Number []: 429
	Work Phone []: 8 800 555-35-35
	Home Phone []: 
	Other []: The richest person in the world
Is the information correct? [Y/n] Y

root@vstu:/home/daniil# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:100:102:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:101:103:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
systemd-timesync:x:102:104:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
messagebus:x:103:106::/nonexistent:/usr/sbin/nologin
syslog:x:104:110::/home/syslog:/usr/sbin/nologin
_apt:x:105:65534::/nonexistent:/usr/sbin/nologin
tss:x:106:111:TPM software stack,,,:/var/lib/tpm:/bin/false
uuidd:x:107:114::/run/uuidd:/usr/sbin/nologin
tcpdump:x:108:115::/nonexistent:/usr/sbin/nologin
avahi-autoipd:x:109:116:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/usr/sbin/nologin
usbmux:x:110:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
rtkit:x:111:117:RealtimeKit,,,:/proc:/usr/sbin/nologin
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/usr/sbin/nologin
cups-pk-helper:x:113:120:user for cups-pk-helper service,,,:/home/cups-pk-helper:/usr/sbin/nologin
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/run/speech-dispatcher:/bin/false
avahi:x:115:121:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/usr/sbin/nologin
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/usr/sbin/nologin
saned:x:117:123::/var/lib/saned:/usr/sbin/nologin
nm-openvpn:x:118:124:NetworkManager OpenVPN,,,:/var/lib/openvpn/chroot:/usr/sbin/nologin
hplip:x:119:7:HPLIP system user,,,:/run/hplip:/bin/false
whoopsie:x:120:125::/nonexistent:/bin/false
colord:x:121:126:colord colour management daemon,,,:/var/lib/colord:/usr/sbin/nologin
geoclue:x:122:127::/var/lib/geoclue:/usr/sbin/nologin
pulse:x:123:128:PulseAudio daemon,,,:/var/run/pulse:/usr/sbin/nologin
gnome-initial-setup:x:124:65534::/run/gnome-initial-setup/:/bin/false
gdm:x:125:130:Gnome Display Manager:/var/lib/gdm3:/bin/false
sssd:x:126:131:SSSD system user,,,:/var/lib/sss:/usr/sbin/nologin
daniil:x:1000:1000:Daniil,,,:/home/daniil:/bin/bash
systemd-coredump:x:999:999:systemd Core Dumper:/:/usr/sbin/nologin
master:x:1001:1001:Elon Musk,429,8 800 555-35-35,,The richest person in the world:/home/master:/bin/bash

root@vstu:/home/daniil# cat /etc/shadow
root:!:19092:0:99999:7:::
daemon:*:19046:0:99999:7:::
bin:*:19046:0:99999:7:::
sys:*:19046:0:99999:7:::
sync:*:19046:0:99999:7:::
games:*:19046:0:99999:7:::
man:*:19046:0:99999:7:::
lp:*:19046:0:99999:7:::
mail:*:19046:0:99999:7:::
news:*:19046:0:99999:7:::
uucp:*:19046:0:99999:7:::
proxy:*:19046:0:99999:7:::
www-data:*:19046:0:99999:7:::
backup:*:19046:0:99999:7:::
list:*:19046:0:99999:7:::
irc:*:19046:0:99999:7:::
gnats:*:19046:0:99999:7:::
nobody:*:19046:0:99999:7:::
systemd-network:*:19046:0:99999:7:::
systemd-resolve:*:19046:0:99999:7:::
systemd-timesync:*:19046:0:99999:7:::
messagebus:*:19046:0:99999:7:::
syslog:*:19046:0:99999:7:::
_apt:*:19046:0:99999:7:::
tss:*:19046:0:99999:7:::
uuidd:*:19046:0:99999:7:::
tcpdump:*:19046:0:99999:7:::
avahi-autoipd:*:19046:0:99999:7:::
usbmux:*:19046:0:99999:7:::
rtkit:*:19046:0:99999:7:::
dnsmasq:*:19046:0:99999:7:::
cups-pk-helper:*:19046:0:99999:7:::
speech-dispatcher:!:19046:0:99999:7:::
avahi:*:19046:0:99999:7:::
kernoops:*:19046:0:99999:7:::
saned:*:19046:0:99999:7:::
nm-openvpn:*:19046:0:99999:7:::
hplip:*:19046:0:99999:7:::
whoopsie:*:19046:0:99999:7:::
colord:*:19046:0:99999:7:::
geoclue:*:19046:0:99999:7:::
pulse:*:19046:0:99999:7:::
gnome-initial-setup:*:19046:0:99999:7:::
gdm:*:19046:0:99999:7:::
sssd:*:19046:0:99999:7:::
daniil:$6$nVjR8sya9UgwqvDb$.nUGSDFIuhGB4OYZBlO8nDfqFwtE5DwPdaiI8QW4yhLjFCkj1I/Cb7BazVDSsN/AV8/DqDqpo2FlwPDmVXE3..:19092:0:99999:7:::
systemd-coredump:!!:19092::::::
master:$6$XCoE/csO9.OWUFeG$yXRqLuXQ3.pop3EVzJjleZiVdyjheQ71JHxtJjSgWpQqP1yfiNEPZ0ZAVlvMUMBsEhb9.ilk.y9NpQBY.BXT..:19109:0:99999:7:::
```

### Часть 2

```
daniil@vstu:~$ touch accessfile
daniil@vstu:~$ echo “plain text” > accessfile
daniil@vstu:~$ cat accessfile 
“plain text”
daniil@vstu:~$ ls -la | grep accessfile
-rw-rw-r--  1 daniil daniil   17 апр 27 22:36 accessfile
daniil@vstu:~$ 
```

### Часть 3

```
daniil@vstu:~$ su master
Password: 
master@vstu:/home/daniil$ cat accessfile 
“plain text”
```
```
master@vstu:/home/daniil$ su daniil
Password: 
daniil@vstu:~$ sudo chmod 770 accessfile
daniil@vstu:~$ su master
Password: 
master@vstu:/home/daniil$ cat accessfile 
cat: accessfile: Permission denied
```

### Часть 4

```
daniil@vstu:~$ sudo chmod 007 accessfile
daniil@vstu:~$ ls -la | grep accessfile
-------rwx  1 daniil daniil   17 апр 27 22:36 accessfile
daniil@vstu:~$ cat accessfile
cat: accessfile: Permission denied
daniil@vstu:~$ su master
Password: 
master@vstu:/home/daniil$ cat accessfile 
“plain text”
```

### Часть 5

```
daniil@vstu:~$ sudo chown daniil:master accessfile
daniil@vstu:~$ sudo chmod 240 accessfile
daniil@vstu:~$ ls -la | grep accessfile
--w-r-----  1 daniil master   17 апр 27 22:36 accessfile
daniil@vstu:~$ cat accessfile
cat: accessfile: Permission denied
daniil@vstu:~$ echo "add some text" >> accessfile
daniil@vstu:~$ su master
Password: 
master@vstu:/home/daniil$ cat accessfile
“plain text”
add some text
master@vstu:/home/daniil$ echo "master text" >> accessfile 
bash: accessfile: Permission denied
master@vstu:/home/daniil$ cat accessfile
“plain text”
add some text
```

### Часть 6

```
daniil@vstu:~$ cls

Command 'cls' not found, but there are 17 similar ones.

daniil@vstu:~$ vim .bashrc
```
```
daniil@vstu:~$ source .bashrc
daniil@vstu:~$ cls
```
```
daniil@vstu:~$ vim .bashrc
daniil@vstu:~$ source .bashrc
daniil@vstu:~$ cls
```
```
The screen is clear now!
daniil@vstu:~$ 
```

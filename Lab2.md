# Лабораторная работа № 2
## Знакомство с командной оболочкой, корневой файловой системой и файлами устройств Linux

### Часть 1

```
daniil@vstu:~$ uname -a 
Linux vstu 5.13.0-39-generic #44~20.04.1-Ubuntu SMP Thu Mar 24 16:43:35 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
daniil@vstu:~$ du -h
4,0K	./.ssh
4,0K	./Music
4,0K	./Templates
4,0K	./Public
4,0K	./mount
8,0K	./notify
4,0K	./Desktop
4,0K	./.gnupg/private-keys-v1.d
16K	./.gnupg
408K	./Pictures
4,0K	./Videos
4,0K	./Downloads
4,0K	./.local/share/evolution/memos/trash
8,0K	./.local/share/evolution/memos
4,0K	./.local/share/evolution/addressbook/system/photos
92K	./.local/share/evolution/addressbook/system
4,0K	./.local/share/evolution/addressbook/trash
100K	./.local/share/evolution/addressbook
4,0K	./.local/share/evolution/calendar/system
4,0K	./.local/share/evolution/calendar/trash
12K	./.local/share/evolution/calendar
8,0K	./.local/share/evolution/tasks/system
4,0K	./.local/share/evolution/tasks/trash
16K	./.local/share/evolution/tasks
4,0K	./.local/share/evolution/mail/trash
8,0K	./.local/share/evolution/mail
148K	./.local/share/evolution
4,0K	./.local/share/icc
4,0K	./.local/share/sounds
112K	./.local/share/gvfs-metadata
4,0K	./.local/share/nautilus/scripts
8,0K	./.local/share/nautilus
12K	./.local/share/keyrings
8,0K	./.local/share/gnome-shell
4,0K	./.local/share/gnome-settings-daemon
8,0K	./.local/share/mc
4,0K	./.local/share/applications
4,0K	./.local/share/flatpak/db
8,0K	./.local/share/flatpak
60K	./.local/share/xorg
4,0K	./.local/share/ibus-table
408K	./.local/share/tracker/data
412K	./.local/share/tracker
808K	./.local/share
20K	./.local/lib/python3.8/site-packages/__pycache__
32K	./.local/lib/python3.8/site-packages/notify2-0.3.1.dist-info
72K	./.local/lib/python3.8/site-packages
76K	./.local/lib/python3.8
80K	./.local/lib
892K	./.local
8,0K	./.config/evolution/sources
12K	./.config/evolution
4,0K	./.config/htop
4,0K	./.config/nautilus
4,0K	./.config/update-notifier
4,0K	./.config/procps
8,0K	./.config/gtk-3.0
4,0K	./.config/goa-1.0
4,0K	./.config/mc
84K	./.config/pulse
8,0K	./.config/dconf
8,0K	./.config/ibus/bus
12K	./.config/ibus
164K	./.config
4,0K	./Documents
1,6M	.
daniil@vstu:~$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:1b:9b:4e brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 86246sec preferred_lft 86246sec
    inet6 fe80::2f33:d48b:a0a5:a6ee/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```
![image](https://user-images.githubusercontent.com/39276703/165594634-71116f32-06a1-4bce-b987-df8c4aa873f8.png)

### Часть 2

```
daniil@vstu:~$ ls -la
total 128
drwxr-xr-x 17 daniil daniil 4096 апр 27 21:30 .
drwxr-xr-x  3 root   root   4096 апр 10 21:02 ..
-rw-------  1 daniil daniil 1784 апр 27 21:29 .bash_history
-rw-r--r--  1 daniil daniil  220 апр 10 21:02 .bash_logout
-rw-r--r--  1 daniil daniil 3771 апр 17 20:40 .bashrc
drwxr-xr-x  3 daniil daniil 4096 апр 27 21:29 .cache
drwx------ 13 daniil daniil 4096 апр 17 20:36 .config
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Desktop
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Documents
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Downloads
drwx------  3 daniil daniil 4096 апр 27 21:23 .gnupg
drwx------  4 daniil daniil 4096 апр 10 21:31 .local
drwxrwxr-x  2 daniil daniil 4096 апр 17 20:41 mount
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Music
drwxrwxr-x  2 daniil daniil 4096 апр 10 22:41 notify
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:35 Pictures
-rw-rw-r--  1 daniil daniil 8674 апр 17 20:19 processes
-rw-r--r--  1 daniil daniil  807 апр 10 21:02 .profile
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Public
-rw-------  1 daniil daniil  272 апр 10 22:35 .python_history
-rw-rw-r--  1 daniil daniil   74 апр 17 20:40 .selected_editor
drwx------  2 daniil daniil 4096 апр 10 21:12 .ssh
-rw-r--r--  1 daniil daniil    0 апр 10 21:25 .sudo_as_admin_successful
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Templates
-rw-r-----  1 daniil daniil    5 апр 27 21:22 .vboxclient-clipboard.pid
-rw-r-----  1 daniil daniil    5 апр 27 21:22 .vboxclient-display-svga-x11.pid
-rw-r-----  1 daniil daniil    5 апр 27 21:22 .vboxclient-draganddrop.pid
-rw-r-----  1 daniil daniil    5 апр 27 21:22 .vboxclient-seamless.pid
drwxr-xr-x  2 daniil daniil 4096 апр 10 21:10 Videos
-rw-------  1 daniil daniil 5774 апр 10 22:41 .viminfo
daniil@vstu:~$ touch geneva
daniil@vstu:~$ echo “humankind” > geneva 
daniil@vstu:~$ cat geneva 
“humankind”
daniil@vstu:~$ ls -la | grep geneva 
-rw-rw-r--  1 daniil daniil   16 апр 27 21:30 geneva
daniil@vstu:~$ mkdir conventiondaniil@vstu:~$ cp geneva convention 
daniil@vstu:~$ cd convention/ 
daniil@vstu:~/convention$ ls
geneva
daniil@vstu:~/convention$ cd ..
daniil@vstu:~$ ls
convention  Documents  geneva  Music   Pictures   Public     Videos
Desktop     Downloads  mount   notify  processes  Templates
daniil@vstu:~$ cd convention/
daniil@vstu:~/convention$ rm -f geneva 
daniil@vstu:~/convention$ ls
daniil@vstu:~/convention$ cd ..
```
```
daniil@vstu:~$ mv geneva convention/ 
daniil@vstu:~$ ls
convention  Documents  mount  notify    processes  Templates
Desktop     Downloads  Music  Pictures  Public     Videos
daniil@vstu:~$ cd convention/
daniil@vstu:~/convention$ ls
geneva
daniil@vstu:~/convention$ mv geneva culture
daniil@vstu:~/convention$ cat culture 
“humankind”
daniil@vstu:~/convention$ cd ..
daniil@vstu:~$ rm -rf convention
daniil@vstu:~$ ls
Desktop    Downloads  Music   Pictures   Public     Videos
Documents  mount      notify  processes  Templates
```

### Часть 3

```
daniil@vstu:~$ sudo ps -aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.4  0.3 168672 12748 ?        Ss   21:22   0:03 /sbin/init sp
root           2  0.0  0.0      0     0 ?        S    21:22   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   21:22   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   21:22   0:00 [rcu_par_gp]
root           6  0.0  0.0      0     0 ?        I<   21:22   0:00 [kworker/0:0H
root           7  0.0  0.0      0     0 ?        I    21:22   0:00 [kworker/u2:0
root           8  0.0  0.0      0     0 ?        I<   21:22   0:00 [mm_percpu_wq
root           9  0.0  0.0      0     0 ?        S    21:22   0:00 [rcu_tasks_ru
root          10  0.0  0.0      0     0 ?        S    21:22   0:00 [rcu_tasks_tr
root          11  0.0  0.0      0     0 ?        S    21:22   0:00 [ksoftirqd/0]
root          12  0.0  0.0      0     0 ?        I    21:22   0:00 [rcu_sched]
root          13  0.0  0.0      0     0 ?        S    21:22   0:00 [migration/0]
root          14  0.0  0.0      0     0 ?        S    21:22   0:00 [idle_inject/
root          16  0.0  0.0      0     0 ?        S    21:22   0:00 [cpuhp/0]
root          17  0.0  0.0      0     0 ?        S    21:22   0:00 [kdevtmpfs]
root          18  0.0  0.0      0     0 ?        I<   21:22   0:00 [netns]
root          19  0.0  0.0      0     0 ?        I<   21:22   0:00 [inet_frag_wq
root          20  0.0  0.0      0     0 ?        S    21:22   0:00 [kauditd]
root          21  0.0  0.0      0     0 ?        S    21:22   0:00 [khungtaskd]
root          22  0.0  0.0      0     0 ?        S    21:22   0:00 [oom_reaper]
root          23  0.0  0.0      0     0 ?        I<   21:22   0:00 [writeback]
root          24  0.0  0.0      0     0 ?        S    21:22   0:00 [kcompactd0]
root          25  0.0  0.0      0     0 ?        SN   21:22   0:00 [ksmd]
root          26  0.0  0.0      0     0 ?        SN   21:22   0:00 [khugepaged]
root          72  0.0  0.0      0     0 ?        I<   21:22   0:00 [kintegrityd]
root          73  0.0  0.0      0     0 ?        I<   21:22   0:00 [kblockd]
root          74  0.0  0.0      0     0 ?        I<   21:22   0:00 [blkcg_punt_b
root          75  0.0  0.0      0     0 ?        I<   21:22   0:00 [tpm_dev_wq]
root          76  0.0  0.0      0     0 ?        I<   21:22   0:00 [ata_sff]
root          77  0.0  0.0      0     0 ?        I<   21:22   0:00 [md]
root          78  0.0  0.0      0     0 ?        I<   21:22   0:00 [edac-poller]
root          79  0.0  0.0      0     0 ?        I<   21:22   0:00 [devfreq_wq]
root          80  0.0  0.0      0     0 ?        S    21:22   0:00 [watchdogd]
root          81  0.3  0.0      0     0 ?        I    21:22   0:02 [kworker/u2:1
root          82  0.2  0.0      0     0 ?        I<   21:22   0:01 [kworker/0:1H
root          84  0.0  0.0      0     0 ?        S    21:22   0:00 [kswapd0]
root          85  0.0  0.0      0     0 ?        S    21:22   0:00 [ecryptfs-kth
root          87  0.0  0.0      0     0 ?        I<   21:22   0:00 [kthrotld]
root          88  0.0  0.0      0     0 ?        I<   21:22   0:00 [acpi_thermal
root          90  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_0]
root          91  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_0]
root          92  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_1]
root          93  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_1]
root          95  0.0  0.0      0     0 ?        I<   21:22   0:00 [vfio-irqfd-c
root          96  0.0  0.0      0     0 ?        I<   21:22   0:00 [mld]
root          97  0.0  0.0      0     0 ?        I<   21:22   0:00 [ipv6_addrcon
root         109  0.0  0.0      0     0 ?        I<   21:22   0:00 [kstrp]
root         112  0.0  0.0      0     0 ?        I<   21:22   0:00 [zswap-shrink
root         113  0.0  0.0      0     0 ?        I<   21:22   0:00 [kworker/u3:0
root         118  0.0  0.0      0     0 ?        I<   21:22   0:00 [charger_mana
root         161  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_2]
root         162  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_2]
root         182  0.0  0.0      0     0 ?        S    21:22   0:00 [jbd2/sda5-8]
root         183  0.0  0.0      0     0 ?        I<   21:22   0:00 [ext4-rsv-con
root         223  0.0  0.4  51728 18560 ?        S<s  21:22   0:00 /lib/systemd/
root         251  0.0  0.1  23940  7312 ?        Ss   21:22   0:00 /lib/systemd/
root         252  0.0  0.0      0     0 ?        I<   21:22   0:00 [ttm_swap]
root         253  0.0  0.0      0     0 ?        S    21:22   0:00 [irq/18-vmwgf
root         254  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc0]
root         255  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc1]
root         256  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc2]
root         257  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc3]
root         258  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc4]
root         259  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc5]
root         260  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc6]
root         261  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc7]
root         266  0.2  0.0      0     0 ?        I    21:22   0:01 [kworker/0:4-
root         268  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop0]
root         274  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop2]
root         275  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop3]
root         286  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop4]
root         288  0.0  0.0      0     0 ?        I    21:22   0:00 [kworker/0:6-
root         289  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop5]
root         293  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop6]
systemd+     502  0.0  0.3  23868 12084 ?        Ss   21:22   0:00 /lib/systemd/
systemd+     523  0.0  0.1  90220  6032 ?        Ssl  21:22   0:00 /lib/systemd/
root         536  0.0  0.2 241920  9288 ?        Ssl  21:22   0:00 /usr/lib/acco
root         537  0.0  0.0   2548   700 ?        Ss   21:22   0:00 /usr/sbin/acp
avahi        541  0.0  0.0   8528  3568 ?        Ss   21:22   0:00 avahi-daemon:
root         543  0.0  0.0   9424  2992 ?        Ss   21:22   0:00 /usr/sbin/cro
message+     547  0.1  0.1   8888  6032 ?        Ss   21:22   0:00 /usr/bin/dbus
root         548  0.2  0.5 338428 21448 ?        Ssl  21:22   0:02 /usr/sbin/Net
root         559  0.0  0.5  39332 20152 ?        Ss   21:22   0:00 /usr/bin/pyth
root         561  0.0  0.3 245020 12488 ?        Ssl  21:22   0:00 /usr/lib/poli
syslog       571  0.0  0.1 224352  4840 ?        Ssl  21:22   0:00 /usr/sbin/rsy
root         577  0.0  0.1 235724  6472 ?        Ssl  21:22   0:00 /usr/libexec/
root         578  0.0  0.2  16696  8280 ?        Ss   21:22   0:00 /lib/systemd/
root         579  0.0  0.3 395404 14372 ?        Ssl  21:22   0:00 /usr/lib/udis
root         582  0.0  0.1  13684  4940 ?        Ss   21:22   0:00 /sbin/wpa_sup
avahi        601  0.0  0.0   8348   332 ?        S    21:22   0:00 avahi-daemon:
root         629  0.0  0.2  28584  8992 ?        Ss   21:22   0:00 /usr/sbin/cup
root         657  0.0  0.3 178392 12696 ?        Ssl  21:22   0:00 /usr/sbin/cup
root         665  0.0  0.2 314460 10888 ?        Ssl  21:22   0:00 /usr/sbin/Mod
root         669  0.0  0.0 295712  2484 ?        Sl   21:22   0:00 /usr/sbin/VBo
root         689  0.0  0.5 118024 22852 ?        Ssl  21:22   0:00 /usr/bin/pyth
root         705  0.0  0.2 239612  8776 ?        Ssl  21:22   0:00 /usr/sbin/gdm
root         718  0.0  0.2 166956  9412 ?        Sl   21:22   0:00 gdm-session-w
daniil       738  0.0  0.2  19108 10336 ?        Ss   21:22   0:00 /lib/systemd/
daniil       740  0.0  0.0 168900  3496 ?        S    21:22   0:00 (sd-pam)
whoopsie     751  0.0  0.4 327296 15920 ?        Ssl  21:22   0:00 /usr/bin/whoo
kernoops     753  0.0  0.0  11260   444 ?        Ss   21:22   0:00 /usr/sbin/ker
kernoops     757  0.0  0.0  11260  2636 ?        Ss   21:22   0:00 /usr/sbin/ker
daniil       792  0.1  0.4 1408932 19444 ?       S<sl 21:22   0:01 /usr/bin/puls
daniil       798  0.0  0.6 584984 24180 ?        SNsl 21:22   0:00 /usr/libexec/
daniil       820  0.0  0.1 240192  7208 ?        SLl  21:22   0:00 /usr/bin/gnom
daniil       834  0.0  0.1 164020  6568 tty2     Ssl+ 21:22   0:00 /usr/lib/gdm3
daniil       838  0.0  0.2  11352  8484 ?        Ss   21:22   0:00 /usr/bin/dbus
daniil       842  1.2  1.8 261824 74708 tty2     Sl+  21:22   0:10 /usr/lib/xorg
rtkit        844  0.0  0.0 152936  2908 ?        SNsl 21:22   0:00 /usr/libexec/
daniil       851  0.0  0.1 239704  7836 ?        Ssl  21:22   0:00 /usr/libexec/
daniil       856  0.0  0.2 382064  8560 ?        Sl   21:22   0:00 /usr/libexec/
daniil       860  0.0  0.2 317396 11592 ?        Ssl  21:22   0:00 /usr/libexec/
daniil       880  0.0  0.2 316728  8904 ?        Ssl  21:22   0:00 /usr/libexec/
daniil       885  0.0  0.1 235880  6244 ?        Ssl  21:22   0:00 /usr/libexec/
daniil       890  0.0  0.9 547476 36892 ?        Sl   21:22   0:00 /usr/libexec/
daniil       904  0.0  0.2 318612 11592 ?        Sl   21:22   0:00 /usr/libexec/
daniil       906  0.0  0.1 235708  6304 ?        Ssl  21:22   0:00 /usr/libexec/
daniil       913  0.0  0.1 237984  7136 ?        Ssl  21:22   0:00 /usr/libexec/
root         920  0.0  0.2 252132  9140 ?        Ssl  21:22   0:00 /usr/lib/upow
daniil       935  0.0  0.3 190736 15240 tty2     Sl+  21:22   0:00 /usr/libexec/
daniil      1014  0.0  0.0  22848   448 ?        S    21:22   0:00 /usr/bin/VBox
daniil      1015  0.0  0.1 155116  7304 ?        Sl   21:22   0:00 /usr/bin/VBox
daniil      1026  0.0  0.0  22848   448 ?        S    21:22   0:00 /usr/bin/VBox
daniil      1027  0.0  0.0 155084  2852 ?        Sl   21:22   0:00 /usr/bin/VBox
daniil      1033  0.0  0.0  22848   448 ?        S    21:22   0:00 /usr/bin/VBox
daniil      1034  0.3  0.0 155600  2972 ?        Sl   21:22   0:03 /usr/bin/VBox
daniil      1041  0.0  0.0  22848   448 ?        S    21:22   0:00 /usr/bin/VBox
daniil      1042  0.0  0.0 157364  3808 ?        Sl   21:22   0:00 /usr/bin/VBox
daniil      1049  0.0  0.0   6040   452 ?        Ss   21:22   0:00 /usr/bin/ssh-
daniil      1069  0.0  0.2 383500  9664 ?        Ssl  21:22   0:00 /usr/libexec/
daniil      1075  0.0  0.1   7376  4364 ?        S    21:22   0:00 /usr/bin/dbus
daniil      1079  0.0  0.1 162280  6252 ?        Ssl  21:22   0:00 /usr/libexec/
daniil      1086  0.0  0.1  90064  4228 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1093  0.0  0.4 486504 17156 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1107  3.1  8.3 3694944 332784 ?      Ssl  21:23   0:24 /usr/bin/gnom
daniil      1131  0.0  0.2 314700 10268 ?        Sl   21:23   0:00 ibus-daemon -
daniil      1135  0.0  0.2 240372  9032 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1136  0.2  0.8 278004 33100 ?        Sl   21:23   0:02 /usr/libexec/
daniil      1138  0.0  0.7 200408 29712 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1140  0.0  0.2 240360  9296 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1153  0.0  0.1 162908  6464 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1157  0.0  0.1 235600  4568 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1162  0.0  0.5 581720 21348 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1168  0.0  0.6 464132 25932 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1178  0.0  0.7 707700 30724 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1186  0.0  0.1 156228  5612 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1189  0.0  0.7 673408 29236 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1218  0.0  0.6 2598772 26552 ?       Sl   21:23   0:00 /usr/bin/gjs 
daniil      1224  0.0  0.2 317552 10640 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1238  0.0  0.2 313888  9212 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1240  0.0  0.7 570292 30940 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1242  0.0  0.4 374328 17336 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1247  0.0  0.2 314116  9684 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1248  0.0  0.7 348316 30252 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1250  0.0  0.8 903492 32624 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1254  0.0  0.7 348700 30872 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1257  0.0  0.2 248228 11176 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1258  0.0  0.1 457104  6000 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1260  0.0  0.1 235512  5864 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1262  0.0  0.1 231800  5588 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1270  0.0  0.3 468868 12692 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1271  0.0  0.2 318048 10488 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1276  0.0  0.2 321748 11064 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1289  0.0  0.2 387856  9488 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1291  0.0  0.7 347908 29884 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1299  0.0  0.2 318240 10792 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1301  0.0  0.7 348932 31064 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1310  0.0  1.5 712344 59956 ?        Sl   21:23   0:00 /usr/libexec/
colord      1334  0.0  0.4 248964 16436 ?        Ssl  21:23   0:00 /usr/libexec/
daniil      1335  0.0  0.2 166552  9100 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1346  0.0  0.3 342192 15068 ?        Sl   21:23   0:00 /usr/libexec/
daniil      1463  0.0  1.1 681392 45324 ?        SLl  21:23   0:00 /usr/bin/seah
daniil      1557  0.0  0.8 496512 33052 ?        Sl   21:24   0:00 update-notifi
root        1880  0.0  0.0      0     0 ?        S<   21:28   0:00 [loop7]
root        1969  0.0  0.0      0     0 ?        S<   21:28   0:00 [loop8]
root        1983  0.4  1.0 735028 39952 ?        Ssl  21:28   0:01 /usr/lib/snap
daniil      2181  0.5  1.2 814700 51292 ?        Ssl  21:29   0:02 /usr/libexec/
daniil      2199  0.1  0.7 439528 31440 ?        Ssl  21:29   0:00 /usr/libexec/
daniil      2249  0.0  0.1  10756  5132 pts/0    Ss   21:29   0:00 bash
root        2340  0.0  0.0      0     0 ?        I    21:34   0:00 [kworker/u2:2
root        2348  0.0  0.1  11936  4644 pts/0    S+   21:36   0:00 sudo ps -aux
root        2349  0.0  0.0  11696  3624 pts/0    R+   21:36   0:00 ps -aux
```
```
daniil@vstu:~$ sudo ps -aux | grep root  
root           1  0.3  0.3 168672 12748 ?        Ss   21:22   0:03 /sbin/init splash
root           2  0.0  0.0      0     0 ?        S    21:22   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        I<   21:22   0:00 [rcu_gp]
root           4  0.0  0.0      0     0 ?        I<   21:22   0:00 [rcu_par_gp]
root           6  0.0  0.0      0     0 ?        I<   21:22   0:00 [kworker/0:0H-events_highpri]
root           7  0.0  0.0      0     0 ?        I    21:22   0:00 [kworker/u2:0-events_unbound]
root           8  0.0  0.0      0     0 ?        I<   21:22   0:00 [mm_percpu_wq]
root           9  0.0  0.0      0     0 ?        S    21:22   0:00 [rcu_tasks_rude_]
root          10  0.0  0.0      0     0 ?        S    21:22   0:00 [rcu_tasks_trace]
root          11  0.0  0.0      0     0 ?        S    21:22   0:00 [ksoftirqd/0]
root          12  0.0  0.0      0     0 ?        I    21:22   0:00 [rcu_sched]
root          13  0.0  0.0      0     0 ?        S    21:22   0:00 [migration/0]
root          14  0.0  0.0      0     0 ?        S    21:22   0:00 [idle_inject/0]
root          16  0.0  0.0      0     0 ?        S    21:22   0:00 [cpuhp/0]
root          17  0.0  0.0      0     0 ?        S    21:22   0:00 [kdevtmpfs]
root          18  0.0  0.0      0     0 ?        I<   21:22   0:00 [netns]
root          19  0.0  0.0      0     0 ?        I<   21:22   0:00 [inet_frag_wq]
root          20  0.0  0.0      0     0 ?        S    21:22   0:00 [kauditd]
root          21  0.0  0.0      0     0 ?        S    21:22   0:00 [khungtaskd]
root          22  0.0  0.0      0     0 ?        S    21:22   0:00 [oom_reaper]
root          23  0.0  0.0      0     0 ?        I<   21:22   0:00 [writeback]
root          24  0.0  0.0      0     0 ?        S    21:22   0:00 [kcompactd0]
root          25  0.0  0.0      0     0 ?        SN   21:22   0:00 [ksmd]
root          26  0.0  0.0      0     0 ?        SN   21:22   0:00 [khugepaged]
root          72  0.0  0.0      0     0 ?        I<   21:22   0:00 [kintegrityd]
root          73  0.0  0.0      0     0 ?        I<   21:22   0:00 [kblockd]
root          74  0.0  0.0      0     0 ?        I<   21:22   0:00 [blkcg_punt_bio]
root          75  0.0  0.0      0     0 ?        I<   21:22   0:00 [tpm_dev_wq]
root          76  0.0  0.0      0     0 ?        I<   21:22   0:00 [ata_sff]
root          77  0.0  0.0      0     0 ?        I<   21:22   0:00 [md]
root          78  0.0  0.0      0     0 ?        I<   21:22   0:00 [edac-poller]
root          79  0.0  0.0      0     0 ?        I<   21:22   0:00 [devfreq_wq]
root          80  0.0  0.0      0     0 ?        S    21:22   0:00 [watchdogd]
root          81  0.2  0.0      0     0 ?        I    21:22   0:02 [kworker/u2:1-events_power_efficient]
root          82  0.2  0.0      0     0 ?        I<   21:22   0:01 [kworker/0:1H-kblockd]
root          84  0.0  0.0      0     0 ?        S    21:22   0:00 [kswapd0]
root          85  0.0  0.0      0     0 ?        S    21:22   0:00 [ecryptfs-kthrea]
root          87  0.0  0.0      0     0 ?        I<   21:22   0:00 [kthrotld]
root          88  0.0  0.0      0     0 ?        I<   21:22   0:00 [acpi_thermal_pm]
root          90  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_0]
root          91  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_0]
root          92  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_1]
root          93  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_1]
root          95  0.0  0.0      0     0 ?        I<   21:22   0:00 [vfio-irqfd-clea]
root          96  0.0  0.0      0     0 ?        I<   21:22   0:00 [mld]
root          97  0.0  0.0      0     0 ?        I<   21:22   0:00 [ipv6_addrconf]
root         109  0.0  0.0      0     0 ?        I<   21:22   0:00 [kstrp]
root         112  0.0  0.0      0     0 ?        I<   21:22   0:00 [zswap-shrink]
root         113  0.0  0.0      0     0 ?        I<   21:22   0:00 [kworker/u3:0]
root         118  0.0  0.0      0     0 ?        I<   21:22   0:00 [charger_manager]
root         161  0.0  0.0      0     0 ?        S    21:22   0:00 [scsi_eh_2]
root         162  0.0  0.0      0     0 ?        I<   21:22   0:00 [scsi_tmf_2]
root         182  0.0  0.0      0     0 ?        S    21:22   0:00 [jbd2/sda5-8]
root         183  0.0  0.0      0     0 ?        I<   21:22   0:00 [ext4-rsv-conver]
root         223  0.0  0.4  51728 18564 ?        S<s  21:22   0:00 /lib/systemd/systemd-journald
root         251  0.0  0.1  23940  7312 ?        Ss   21:22   0:00 /lib/systemd/systemd-udevd
root         252  0.0  0.0      0     0 ?        I<   21:22   0:00 [ttm_swap]
root         253  0.0  0.0      0     0 ?        S    21:22   0:00 [irq/18-vmwgfx]
root         254  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc0]
root         255  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc1]
root         256  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc2]
root         257  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc3]
root         258  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc4]
root         259  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc5]
root         260  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc6]
root         261  0.0  0.0      0     0 ?        S    21:22   0:00 [card0-crtc7]
root         266  0.2  0.0      0     0 ?        I    21:22   0:01 [kworker/0:4-events]
root         268  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop0]
root         274  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop2]
root         275  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop3]
root         286  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop4]
root         288  0.0  0.0      0     0 ?        I    21:22   0:00 [kworker/0:6-events]
root         289  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop5]
root         293  0.0  0.0      0     0 ?        S<   21:22   0:00 [loop6]
root         536  0.0  0.2 241920  9288 ?        Ssl  21:22   0:00 /usr/lib/accountsservice/accounts-daemon
root         537  0.0  0.0   2548   700 ?        Ss   21:22   0:00 /usr/sbin/acpid
root         543  0.0  0.0   9424  2992 ?        Ss   21:22   0:00 /usr/sbin/cron -f
root         548  0.2  0.5 338428 21448 ?        Ssl  21:22   0:02 /usr/sbin/NetworkManager --no-daemon
root         559  0.0  0.5  39332 20152 ?        Ss   21:22   0:00 /usr/bin/python3 /usr/bin/networkd-dispatcher --run-startup-triggers
root         561  0.0  0.3 245020 12488 ?        Ssl  21:22   0:00 /usr/lib/policykit-1/polkitd --no-debug
root         577  0.0  0.1 235724  6472 ?        Ssl  21:22   0:00 /usr/libexec/switcheroo-control
root         578  0.0  0.2  16696  8280 ?        Ss   21:22   0:00 /lib/systemd/systemd-logind
root         579  0.0  0.3 395404 14372 ?        Ssl  21:22   0:00 /usr/lib/udisks2/udisksd
root         582  0.0  0.1  13684  4940 ?        Ss   21:22   0:00 /sbin/wpa_supplicant -u -s -O /run/wpa_supplicant
avahi        601  0.0  0.0   8348   332 ?        S    21:22   0:00 avahi-daemon: chroot helper
root         629  0.0  0.2  28584  8992 ?        Ss   21:22   0:00 /usr/sbin/cupsd -l
root         657  0.0  0.3 178392 12696 ?        Ssl  21:22   0:00 /usr/sbin/cups-browsed
root         665  0.0  0.2 314460 10888 ?        Ssl  21:22   0:00 /usr/sbin/ModemManager
root         669  0.0  0.0 295712  2484 ?        Sl   21:22   0:00 /usr/sbin/VBoxService
root         689  0.0  0.5 118024 22852 ?        Ssl  21:22   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         705  0.0  0.2 239612  8776 ?        Ssl  21:22   0:00 /usr/sbin/gdm3
root         718  0.0  0.2 166956  9412 ?        Sl   21:22   0:00 gdm-session-worker [pam/gdm-autologin]
root         920  0.0  0.2 252132  9140 ?        Ssl  21:22   0:00 /usr/lib/upower/upowerd
root        1880  0.0  0.0      0     0 ?        S<   21:28   0:00 [loop7]
root        1969  0.0  0.0      0     0 ?        S<   21:28   0:00 [loop8]
root        1983  0.3  1.0 735028 39952 ?        Ssl  21:28   0:01 /usr/lib/snapd/snapd
root        2340  0.0  0.0      0     0 ?        I    21:34   0:00 [kworker/u2:2-ext4-rsv-conversion]
root        2355  0.0  0.1  11936  4716 pts/0    S+   21:37   0:00 sudo ps -aux
daniil      2356  0.0  0.0   9048   716 pts/0    S+   21:37   0:00 grep --color=auto root
root        2357  0.0  0.0  11696  3580 pts/0    R+   21:37   0:00 ps -aux
```

![image](https://user-images.githubusercontent.com/39276703/165596368-2847ef2c-5f4b-45cf-a8f3-d7921e441ec6.png)
![image](https://user-images.githubusercontent.com/39276703/165596388-592512d3-a509-40df-9759-569f6961dde6.png)
![image](https://user-images.githubusercontent.com/39276703/165596613-381a3a86-5dfd-42a9-be1f-697cc9b71f87.png)
![image](https://user-images.githubusercontent.com/39276703/165596671-ad3873f0-2ff2-4132-b01b-6365dca82ba8.png)


### Часть 4

```
daniil@vstu:~$ touch geneva
daniil@vstu:~$ echo “humankind” > geneva
daniil@vstu:~$ ln geneva hlink
daniil@vstu:~$ ln -s geneva slink
daniil@vstu:~$ ls -la | grep link
-rw-rw-r--  2 daniil daniil   16 апр 27 21:40 hlink
lrwxrwxrwx  1 daniil daniil    6 апр 27 21:41 slink -> geneva
daniil@vstu:~$ cat slink
“humankind”
daniil@vstu:~$ cat hlink
“humankind”
daniil@vstu:~$ echo “man” > geneva
daniil@vstu:~$ cat slink
“man”
daniil@vstu:~$ cat hlink
“man”
daniil@vstu:~$ rm -f geneva
daniil@vstu:~$ ls -la | grep link
-rw-rw-r--  1 daniil daniil   10 апр 27 21:41 hlink
lrwxrwxrwx  1 daniil daniil    6 апр 27 21:41 slink -> geneva
daniil@vstu:~$ cat slink
cat: slink: No such file or directory
daniil@vstu:~$ cat hlink
“man”
daniil@vstu:~$ touch geneva
daniil@vstu:~$ echo “killall” > geneva
daniil@vstu:~$ cat slink
“killall”
daniil@vstu:~$ cat hlink
“man”
```

### Часть 5

![image](https://user-images.githubusercontent.com/39276703/165597585-8c50869e-e87d-4e3c-bac6-aa3a9682d1a1.png)
![image](https://user-images.githubusercontent.com/39276703/165597685-43b3e930-c231-4af9-98bc-6bec2583e623.png)
![image](https://user-images.githubusercontent.com/39276703/165597892-bfdf6802-838f-47cf-8105-303a02f6200c.png)

### Часть 6

```
daniil@vstu:~$ sudo systemctl stop lightdm 
[sudo] password for daniil: 
Failed to stop lightdm.service: Unit lightdm.service not loaded.
```
```
daniil@vstu:~$ sudo systemctl isolate multi-user.target
```
![image](https://user-images.githubusercontent.com/39276703/165600059-61e49f1f-f41e-4422-9cd2-1da031919c7b.png)

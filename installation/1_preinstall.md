
root@[CCHserver5]#cat /proc/sys/vm/swappiness
10


root@[CCHserver5]#df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G  6.5G   24G  22% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000
root@[CCHserver5]#



root@[CCHserver5]#cat /proc/meminfo  |grep -i huge
AnonHugePages:         0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
root@[CCHserver5]#


root@[CCHserver5]#ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.4.176  netmask 255.255.240.0  broadcast 172.31.15.255
        inet6 fe80::76:d9ff:fee6:3a13  prefixlen 64  scopeid 0x20<link>
        ether 02:76:d9:e6:3a:13  txqueuelen 1000  (Ethernet)
        RX packets 929  bytes 85310 (83.3 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 831  bytes 111640 (109.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 6  bytes 416 (416.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6  bytes 416 (416.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

root@[CCHserver5]#
root@[CCHserver5]#



root@[CCHserver5]#cat /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

172.31.4.178 CCHserver1 CCHserver1.localhost4.localdomain
172.31.4.177 CCHserver2 CCHserver2.localhost4.localdomain
172.31.4.179 CCHserver3 CCHserver3.localhost4.localdomain
172.31.4.175 CCHserver4 CCHserver4.localhost4.localdomain 
172.31.4.176 CCHserver5 CCHserver5.localhost4.localdomain

root@[CCHserver5]#

root@[CCHserver4]#service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset:                                                                                         disabled)
   Active: active (running) since Mon 2016-12-05 10:57:02 UTC; 11s ago
  Process: 9213 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SU                                                                                        CCESS)
 Main PID: 9214 (nscd)
   CGroup: /system.slice/nscd.service
           └─9214 /usr/sbin/nscd


root@[CCHserver3]#service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2016-12-05 10:54:24 UTC; 1min 53s ago
 Main PID: 9213 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─9213 /usr/sbin/ntpd -u ntp:ntp -g







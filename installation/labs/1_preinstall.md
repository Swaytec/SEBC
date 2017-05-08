
Check vm.swappiness on all your nodes
```
sysctl vm.swappiness
echo 1 > /proc/sys/vm/swappiness
```


Show the mount attributes of your volume(s)
```
[root@ip-172-31-42-246 ~]# df -Th
Filesystem     Type   Size  Used Avail Use% Mounted on
/dev/xvde      ext4   7.9G  651M  6.9G   9% /
tmpfs          tmpfs  7.4G     0  7.4G   0% /dev/shm
```



If you have ext-based volumes, list the reserve space setting
```
[root@ip-172-31-42-246 hugepages]# fdisk /dev/xvde
Command (m for help): p

Disk /dev/xvde: 32.2 GB, 32212254720 bytes
255 heads, 63 sectors/track, 3916 cylinders
Units = cylinders of 16065 * 512 = 8225280 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disk identifier: 0x655d7a7c

    Device Boot      Start         End      Blocks   Id  System
```



Disable transparent hugepage support
```
vi /etc/rc.local
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag

./scp.sh /etc/rc.local /etc/

reboot
or
./ssh.sh "echo never > /sys/kernel/mm/transparent_hugepage/enabled
./ssh.sh "echo never > /sys/kernel/mm/transparent_hugepage/defrag
```



List your network interface configuration
```
ifconfig
eth0      Link encap:Ethernet  HWaddr 06:F0:0D:6D:C8:F0  
          inet addr:172.31.42.246  Bcast:172.31.47.255  Mask:255.255.240.0
          inet6 addr: fe80::4f0:dff:fe6d:c8f0/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:2472 errors:0 dropped:0 overruns:0 frame:0
          TX packets:1571 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:192944 (188.4 KiB)  TX bytes:271280 (264.9 KiB)
          Interrupt:24 

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:16436  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0 
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)



```



Show that forward and reverse host lookups are correctly resolved
```
[root@ip-172-31-41-39 ~]# yum install bind-utils 

[root@ip-172-31-41-39 ~]# nslookup yum install bind-utils
nslookup: couldn't get address for 'install': not found
[root@ip-172-31-41-39 ~]# nslookup ec2-35-163-39-218.us-west-2.compute.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-35-163-39-218.us-west-2.compute.amazonaws.com
Address: 172.31.42.246

[root@ip-172-31-41-39 ~]# nslookup 172.31.42.246
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
246.42.31.172.in-addr.arpa	name = ip-172-31-42-246.us-west-2.compute.internal.


```


Show the nscd service is running
```
yum install nscd
service nscd start
chkconfig nscd on

[root@ip-172-31-42-246 hugepages]# service nscd status
nscd (pid 4524) is running...
```


Show the ntpd service is running
```
[root@ip-172-31-42-246 hugepages]# yum install ntp
[root@ip-172-31-42-246 hugepages]# service ntpd status
ntpd is stopped
[root@ip-172-31-42-246 hugepages]# service ntpd start
Starting ntpd:                                             [  OK  ]
[root@ip-172-31-42-246 hugepages]# chkconfig ntpd on
[root@ip-172-31-42-246 hugepages]# service ntpd status
ntpd (pid  4613) is running...
```





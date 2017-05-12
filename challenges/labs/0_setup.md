## AWS information
```
AWS ec2 instance
us-west-2a

[root@ip-172-31-36-112 ~]# cat /etc/issue
CentOS release 6.5 (Final)


public ip:ec2-34-210-102-156.us-west-2.compute.amazonaws.com
hostname:ip-172-31-36-112.us-west-2.compute.internal
private ip:172.31.36.112

public ip:ec2-34-209-96-186.us-west-2.compute.amazonaws.com
hostname:ip-172-31-43-169.us-west-2.compute.internal
private ip:172.31.43.169

public ip:ec2-54-70-198-61.us-west-2.compute.amazonaws.com
hostname:ip-172-31-43-250.us-west-2.compute.internal
private ip:172.31.43.250

public ip:ec2-35-166-58-205.us-west-2.compute.amazonaws.com
hostname:ip-172-31-43-83.us-west-2.compute.internal
private ip:172.31.43.83

public ip:ec2-35-160-6-76.us-west-2.compute.amazonaws.com
hostname:ip-172-31-32-63.us-west-2.compute.internal
private ip:172.31.32.63

```

## Disk space
```
[root@ip-172-31-36-112 ~]# df -hT
Filesystem     Type   Size  Used Avail Use% Mounted on
/dev/xvde      ext4    30G  701M   28G   3% /
tmpfs          tmpfs  7.4G     0  7.4G   0% /dev/shm
```

## My repository
```
[root@ip-172-31-36-112 ~]# yum repolist enabled
Loaded plugins: fastestmirror, presto
Determining fastest mirrors
 * base: mirrors.sonic.net
 * extras: mirrors.kernel.org
 * updates: bay.uchicago.edu
base                                                                                                         | 3.7 kB     00:00     
extras                                                                                                       | 3.4 kB     00:00     
updates                                                                                                      | 3.4 kB     00:00     
repo id                                                  repo name                                                            status
base                                                     CentOS-6 - Base                                                      6,706
extras                                                   CentOS-6 - Extras                                                       64
updates                                                  CentOS-6 - Updates                                                     270
repolist: 7,040

```

## Add User and Group 
```
groupadd shanghai
groupadd beijing
useradd -u 2800 -g beijing zhou
useradd -u 2900 -g shanghai chen
```

## list passwd
```
zhou:x:2800:501::/home/zhou:/bin/bash
chen:x:2900:500::/home/chen:/bin/bash
```

## list Group
```
shanghai:x:500:
beijing:x:501:
```
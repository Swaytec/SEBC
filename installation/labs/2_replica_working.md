Mysql install
```
[root@ip-172-31-41-39 ~]# ls
mysql57-community-release-el6-11.noarch.rpm
[root@ip-172-31-41-39 ~]# rpm -ivh mysql57-community-release-el6-11.noarch.rpm 
warning: mysql57-community-release-el6-11.noarch.rpm: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Preparing...                ########################################### [100%]
   1:mysql57-community-relea########################################### [100%]
[root@ip-172-31-41-39 ~]# vi /etc/yum.repos.d/mysql-community.repo
[root@ip-172-31-42-246 ~]# yum install mysql mysql-server
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: repos.forethought.net
 * extras: mirror.pac-12.org
 * updates: mirrors.xmission.com
Setting up Install Process
Package mysql is obsoleted by mysql-community-client, trying to install mysql-community-client-5.5.56-2.el6.x86_64 instead
Package mysql-server is obsoleted by mysql-community-server, trying to install mysql-community-server-5.5.56-2.el6.x86_64 instead
Resolving Dependencies
--> Running transaction check
---> Package mysql-community-client.x86_64 0:5.5.56-2.el6 will be installed
--> Processing Dependency: mysql-community-libs(x86-64) >= 5.5.8 for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(Sys::Hostname) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(IPC::Open3) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(Getopt::Long) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(File::Temp) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(Fcntl) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(Exporter) for package: mysql-community-client-5.5.56-2.el6.x86_64
--> Processing Dependency: /usr/bin/perl for package: mysql-community-client-5.5.56-2.el6.x86_64
---> Package mysql-community-server.x86_64 0:5.5.56-2.el6 will be installed
--> Processing Dependency: mysql-community-common(x86-64) = 5.5.56-2.el6 for package: mysql-community-server-5.5.56-2.el6.x86_64
--> Processing Dependency: perl(DBI) for package: mysql-community-server-5.5.56-2.el6.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.4)(64bit) for package: mysql-community-server-5.5.56-2.el6.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.1)(64bit) for package: mysql-community-server-5.5.56-2.el6.x86_64
--> Processing Dependency: libaio.so.1()(64bit) for package: mysql-community-server-5.5.56-2.el6.x86_64
--> Running transaction check
---> Package libaio.x86_64 0:0.3.107-10.el6 will be installed
---> Package mysql-community-common.x86_64 0:5.5.56-2.el6 will be installed
---> Package mysql-community-libs.x86_64 0:5.5.56-2.el6 will be obsoleting
---> Package mysql-libs.x86_64 0:5.1.71-1.el6 will be obsoleted
--> Processing Dependency: libmysqlclient.so.16()(64bit) for package: 2:postfix-2.6.6-2.2.el6_1.x86_64
--> Processing Dependency: libmysqlclient.so.16(libmysqlclient_16)(64bit) for package: 2:postfix-2.6.6-2.2.el6_1.x86_64
---> Package perl.x86_64 4:5.10.1-144.el6 will be installed
--> Processing Dependency: perl-libs = 4:5.10.1-144.el6 for package: 4:perl-5.10.1-144.el6.x86_64
--> Processing Dependency: perl-libs for package: 4:perl-5.10.1-144.el6.x86_64
--> Processing Dependency: perl(version) for package: 4:perl-5.10.1-144.el6.x86_64
--> Processing Dependency: perl(Pod::Simple) for package: 4:perl-5.10.1-144.el6.x86_64
--> Processing Dependency: perl(Module::Pluggable) for package: 4:perl-5.10.1-144.el6.x86_64
--> Processing Dependency: libperl.so()(64bit) for package: 4:perl-5.10.1-144.el6.x86_64
---> Package perl-DBI.x86_64 0:1.609-4.el6 will be installed
--> Running transaction check
---> Package mysql-community-libs-compat.x86_64 0:5.5.56-2.el6 will be obsoleting
---> Package perl-Module-Pluggable.x86_64 1:3.90-144.el6 will be installed
---> Package perl-Pod-Simple.x86_64 1:3.13-144.el6 will be installed
--> Processing Dependency: perl(Pod::Escapes) >= 1.04 for package: 1:perl-Pod-Simple-3.13-144.el6.x86_64
---> Package perl-libs.x86_64 4:5.10.1-144.el6 will be installed
---> Package perl-version.x86_64 3:0.77-144.el6 will be installed
---> Package postfix.x86_64 2:2.6.6-2.2.el6_1 will be updated
---> Package postfix.x86_64 2:2.6.6-8.el6 will be an update
--> Running transaction check
---> Package perl-Pod-Escapes.x86_64 1:1.04-144.el6 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================================================
 Package                             Arch           Version                    Repository                 Size
===============================================================================================================
Installing:
 mysql-community-client              x86_64         5.5.56-2.el6               mysql55-community          15 M
 mysql-community-libs                x86_64         5.5.56-2.el6               mysql55-community         1.7 M
     replacing  mysql-libs.x86_64 5.1.71-1.el6
 mysql-community-libs-compat         x86_64         5.5.56-2.el6               mysql55-community         1.6 M
     replacing  mysql-libs.x86_64 5.1.71-1.el6
 mysql-community-server              x86_64         5.5.56-2.el6               mysql55-community          38 M
Installing for dependencies:
 libaio                              x86_64         0.3.107-10.el6             base                       21 k
 mysql-community-common              x86_64         5.5.56-2.el6               mysql55-community         277 k
 perl                                x86_64         4:5.10.1-144.el6           base                       10 M
 perl-DBI                            x86_64         1.609-4.el6                base                      705 k
 perl-Module-Pluggable               x86_64         1:3.90-144.el6             base                       41 k
 perl-Pod-Escapes                    x86_64         1:1.04-144.el6             base                       33 k
 perl-Pod-Simple                     x86_64         1:3.13-144.el6             base                      213 k
 perl-libs                           x86_64         4:5.10.1-144.el6           base                      579 k
 perl-version                        x86_64         3:0.77-144.el6             base                       52 k
Updating for dependencies:
 postfix                             x86_64         2:2.6.6-8.el6              base                      2.0 M

Transaction Summary
===============================================================================================================
Install      13 Package(s)
Upgrade       1 Package(s)

Total download size: 70 M
Is this ok [y/N]: y
Downloading Packages:
Setting up and reading Presto delta metadata
Processing delta metadata
Package(s) data still to download: 70 M
(1/14): libaio-0.3.107-10.el6.x86_64.rpm                                                |  21 kB     00:00     
(2/14): mysql-community-client-5.5.56-2.el6.x86_64.rpm                                  |  15 MB     00:00     
(3/14): mysql-community-common-5.5.56-2.el6.x86_64.rpm                                  | 277 kB     00:00     
(4/14): mysql-community-libs-5.5.56-2.el6.x86_64.rpm                                    | 1.7 MB     00:00     
(5/14): mysql-community-libs-compat-5.5.56-2.el6.x86_64.rpm                             | 1.6 MB     00:00     
(6/14): mysql-community-server-5.5.56-2.el6.x86_64.rpm                                  |  38 MB     00:00     
(7/14): perl-5.10.1-144.el6.x86_64.rpm                                                  |  10 MB     00:01     
(8/14): perl-DBI-1.609-4.el6.x86_64.rpm                                                 | 705 kB     00:00     
(9/14): perl-Module-Pluggable-3.90-144.el6.x86_64.rpm                                   |  41 kB     00:00     
(10/14): perl-Pod-Escapes-1.04-144.el6.x86_64.rpm                                       |  33 kB     00:00     
(11/14): perl-Pod-Simple-3.13-144.el6.x86_64.rpm                                        | 213 kB     00:00     
(12/14): perl-libs-5.10.1-144.el6.x86_64.rpm                                            | 579 kB     00:00     
(13/14): perl-version-0.77-144.el6.x86_64.rpm                                           |  52 kB     00:00     
(14/14): postfix-2.6.6-8.el6.x86_64.rpm                                                 | 2.0 MB     00:00     
---------------------------------------------------------------------------------------------------------------
Total                                                                           14 MB/s |  70 MB     00:05     
warning: rpmts_HdrFromFdno: Header V3 DSA/SHA1 Signature, key ID 5072e1f5: NOKEY
Retrieving key from file:///etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Importing GPG key 0x5072E1F5:
 Userid : MySQL Release Engineering <mysql-build@oss.oracle.com>
 Package: mysql57-community-release-el6-11.noarch (installed)
 From   : /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql
Is this ok [y/N]: y
Running rpm_check_debug
Running Transaction Test
Transaction Test Succeeded
Running Transaction
Warning: RPMDB altered outside of yum.
  Installing : mysql-community-common-5.5.56-2.el6.x86_64                                                 1/16 
  Installing : mysql-community-libs-5.5.56-2.el6.x86_64                                                   2/16 
  Installing : mysql-community-libs-compat-5.5.56-2.el6.x86_64                                            3/16 
  Installing : 1:perl-Pod-Escapes-1.04-144.el6.x86_64                                                     4/16 
  Installing : 4:perl-libs-5.10.1-144.el6.x86_64                                                          5/16 
  Installing : 1:perl-Module-Pluggable-3.90-144.el6.x86_64                                                6/16 
  Installing : 1:perl-Pod-Simple-3.13-144.el6.x86_64                                                      7/16 
  Installing : 3:perl-version-0.77-144.el6.x86_64                                                         8/16 
  Installing : 4:perl-5.10.1-144.el6.x86_64                                                               9/16 
  Installing : mysql-community-client-5.5.56-2.el6.x86_64                                                10/16 
  Installing : perl-DBI-1.609-4.el6.x86_64                                                               11/16 
  Installing : libaio-0.3.107-10.el6.x86_64                                                              12/16 
  Installing : mysql-community-server-5.5.56-2.el6.x86_64                                                13/16 
  Updating   : 2:postfix-2.6.6-8.el6.x86_64                                                              14/16 
  Cleanup    : 2:postfix-2.6.6-2.2.el6_1.x86_64                                                          15/16 
  Erasing    : mysql-libs-5.1.71-1.el6.x86_64                                                            16/16 
  Verifying  : 3:perl-version-0.77-144.el6.x86_64                                                         1/16 
  Verifying  : mysql-community-libs-5.5.56-2.el6.x86_64                                                   2/16 
  Verifying  : mysql-community-server-5.5.56-2.el6.x86_64                                                 3/16 
  Verifying  : 4:perl-5.10.1-144.el6.x86_64                                                               4/16 
  Verifying  : mysql-community-client-5.5.56-2.el6.x86_64                                                 5/16 
  Verifying  : mysql-community-libs-compat-5.5.56-2.el6.x86_64                                            6/16 
  Verifying  : 1:perl-Pod-Simple-3.13-144.el6.x86_64                                                      7/16 
  Verifying  : 2:postfix-2.6.6-8.el6.x86_64                                                               8/16 
  Verifying  : mysql-community-common-5.5.56-2.el6.x86_64                                                 9/16 
  Verifying  : 4:perl-libs-5.10.1-144.el6.x86_64                                                         10/16 
  Verifying  : 1:perl-Module-Pluggable-3.90-144.el6.x86_64                                               11/16 
  Verifying  : perl-DBI-1.609-4.el6.x86_64                                                               12/16 
  Verifying  : 1:perl-Pod-Escapes-1.04-144.el6.x86_64                                                    13/16 
  Verifying  : libaio-0.3.107-10.el6.x86_64                                                              14/16 
  Verifying  : 2:postfix-2.6.6-2.2.el6_1.x86_64                                                          15/16 
  Verifying  : mysql-libs-5.1.71-1.el6.x86_64                                                            16/16 

Installed:
  mysql-community-client.x86_64 0:5.5.56-2.el6             mysql-community-libs.x86_64 0:5.5.56-2.el6         
  mysql-community-libs-compat.x86_64 0:5.5.56-2.el6        mysql-community-server.x86_64 0:5.5.56-2.el6       

Dependency Installed:
  libaio.x86_64 0:0.3.107-10.el6                        mysql-community-common.x86_64 0:5.5.56-2.el6          
  perl.x86_64 4:5.10.1-144.el6                          perl-DBI.x86_64 0:1.609-4.el6                         
  perl-Module-Pluggable.x86_64 1:3.90-144.el6           perl-Pod-Escapes.x86_64 1:1.04-144.el6                
  perl-Pod-Simple.x86_64 1:3.13-144.el6                 perl-libs.x86_64 4:5.10.1-144.el6                     
  perl-version.x86_64 3:0.77-144.el6                   

Dependency Updated:
  postfix.x86_64 2:2.6.6-8.el6                                                                                 

Replaced:
  mysql-libs.x86_64 0:5.1.71-1.el6                                                                             

Complete!
```


configure mysql
```
[root@ip-172-31-42-246 ~]# mysqladmin -u root password 'rootme'

mysql> delete from mysql.user where user='';
Query OK, 2 rows affected (0.00 sec)

mysql> flush privileges;
Query OK, 0 rows affected (0.00 sec)

mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'rootme' WITH GRANT OPTION; 
Query OK, 0 rows affected (0.00 sec)

mysql> drop database test;


```


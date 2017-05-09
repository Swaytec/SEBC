install JDK
```
[root@ip-172-31-42-246 ~]# rpm -ivh jdk-8u65-linux-x64.rpm
Preparing...                ########################################### [100%]
   1:jdk1.8.0_65            ########################################### [100%]
Unpacking JAR files...
        tools.jar...
        plugin.jar...
        javaws.jar...
        deploy.jar...
        rt.jar...
        jsse.jar...
        charsets.jar...
        localedata.jar...
        jfxrt.jar...
[root@ip-172-31-42-246 ~]# 
[root@ip-172-31-42-246 ~]# 
[root@ip-172-31-42-246 ~]# java -version
java version "1.8.0_65"
Java(TM) SE Runtime Environment (build 1.8.0_65-b17)
Java HotSpot(TM) 64-Bit Server VM (build 25.65-b01, mixed mode)
```

disable selinux
```
vi /etc/selinux/config
SELINUX=disabled
reboot
```

Install a supported JDBC connector on all nodes
```
mv mysql-connector-java-5.1.40-bin.jar /opt/cm/share/cmf/lib/
```



Create the databases and access grants you will need
```
mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'rootme' WITH GRANT OPTION; 
Query OK, 0 rows affected (0.00 sec)

mysql> create database hive DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
Query OK, 1 row affected (0.00 sec)

mysql> create database oozie DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
Query OK, 1 row affected (0.00 sec)

mysql> create database hue DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
Query OK, 1 row affected (0.00 sec)


```

install cm
```
tar -zxvf cloudera-manager-el6-cm5.9.0_x86_64.tar.gz -C /opt/
mv /opt/cm-5.9.0/ /opt/cm
mv CDH-5.9.0-1.cdh5.9.0.p0.23-el6.parcel CDH-5.9.0-1.cdh5.9.0.p0.23-el6.parcel.sha1 /opt/cloudera/parcel-repo/
mv manifest.json /opt/cloudera/parcel-repo/
cd /opt/cloudera/parcel-repo/
mv CDH-5.9.0-1.cdh5.9.0.p0.23-el6.parcel.sha1 CDH-5.9.0-1.cdh5.9.0.p0.23-el6.parcel.sha

vi /opt/cm/etc/cloudera-scm-agent/config.ini

server_host=ip-172-31-42-246.us-west-2.compute.internal

```


Configure Cloudera Manager to connect to the database
```
mv mysql-connector-java-5.1.42-bin.jar /opt/cm/share/cmf/lib/
/opt/cm/share/cmf/schema/scm_prepare_database.sh mysql cm -hlocalhost -uroot -ppassword00 --scm-host localhost scm scm scm
useradd --system --home=/opt/cm/run/cloudera-scm-server --no-create-home --shell=/bin/false --comment "Cloudera SCM User" cloudera-scm
scp /opt/cm to other node
```


Start your Cloudera Manager server
```
/opt/cm/etc/init.d/cloudera-scm-server start
/opt/cm/etc/init.d/cloudera-scm-agent start
```


disk extend
```
resize2fs /dev/xvde
```




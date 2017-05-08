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


Configure Cloudera Manager to connect to the database
```
/opt/cm/share/cmf/schema/scm_prepare_database.sh mysql cm -hlocalhost -uroot -ppassword00 --scm-host localhost scm scm scm

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




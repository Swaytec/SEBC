## The hostname of db server node
```
ip-172-31-36-112.us-west-2.compute.internal
```

## database server's version
```
[root@ip-172-31-36-112 ~]# mysql --version
mysql  Ver 14.14 Distrib 5.6.36, for Linux (x86_64) using  EditLine wrapper
```

## list created databases
```
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| cm                 |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| report             |
| rman               |
| scm                |
| sentry             |
+--------------------+
11 rows in set (0.00 sec)


```

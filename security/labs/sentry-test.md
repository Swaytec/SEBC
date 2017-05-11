
## Verify user privileges
```
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ

0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511041313_356b33a2-6ef4-4634-8e92-2b62e270a714): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041313_356b33a2-6ef4-4634-8e92-2b62e270a714); Time taken: 0.758 seconds
INFO  : Executing command(queryId=hive_20170511041313_356b33a2-6ef4-4634-8e92-2b62e270a714): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041313_356b33a2-6ef4-4634-8e92-2b62e270a714); Time taken: 0.285 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.48 seconds)
```


## george should be able to see all tables
```
[root@ip-172-31-41-53 hue]# kinit george
Password for george@SWAYTEC.COM: 
[root@ip-172-31-41-53 hue]# beeline
Beeline version 1.1.0-cdh5.11.0 by Apache Hive
beeline>  !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> 
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511043131_f0f57669-8f96-4684-b754-ae39561ea554): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511043131_f0f57669-8f96-4684-b754-ae39561ea554); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511043131_f0f57669-8f96-4684-b754-ae39561ea554): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511043131_f0f57669-8f96-4684-b754-ae39561ea554); Time taken: 0.161 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.353 seconds)
```



## ferdinand should see sample_07
```
[root@ip-172-31-41-53 hue]# kinit ferdinand
Password for ferdinand@SWAYTEC.COM: 
[root@ip-172-31-41-53 hue]# 
[root@ip-172-31-41-53 hue]# beeline
Beeline version 1.1.0-cdh5.11.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-53.us-west-2.compute.internal@SWAYTEC.COM
Connected to: Apache Hive (version 1.1.0-cdh5.11.0)
Driver: Hive JDBC (version 1.1.0-cdh5.11.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511043232_b00c3fd6-0233-4725-a249-00915ec6e91d): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511043232_b00c3fd6-0233-4725-a249-00915ec6e91d); Time taken: 0.087 seconds
INFO  : Executing command(queryId=hive_20170511043232_b00c3fd6-0233-4725-a249-00915ec6e91d): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511043232_b00c3fd6-0233-4725-a249-00915ec6e91d); Time taken: 0.135 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.332 seconds)
```





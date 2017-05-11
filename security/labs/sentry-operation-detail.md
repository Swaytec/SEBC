## record operation 
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



0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511041616_3a1314a8-abff-439f-865b-36b39f9185d6): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041616_3a1314a8-abff-439f-865b-36b39f9185d6); Time taken: 0.078 seconds
INFO  : Executing command(queryId=hive_20170511041616_3a1314a8-abff-439f-865b-36b39f9185d6): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041616_3a1314a8-abff-439f-865b-36b39f9185d6); Time taken: 0.814 seconds
INFO  : OK
No rows affected (0.907 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20170511041616_f440a8be-adf8-4bcf-ac3e-48354b44e0cf): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041616_f440a8be-adf8-4bcf-ac3e-48354b44e0cf); Time taken: 0.121 seconds
INFO  : Executing command(queryId=hive_20170511041616_f440a8be-adf8-4bcf-ac3e-48354b44e0cf): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041616_f440a8be-adf8-4bcf-ac3e-48354b44e0cf); Time taken: 0.097 seconds
INFO  : OK
No rows affected (0.234 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP root;
INFO  : Compiling command(queryId=hive_20170511041717_8ab7b9a9-87d4-492d-816b-ef0592cee0b3): GRANT ROLE sentry_admin TO GROUP root
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041717_8ab7b9a9-87d4-492d-816b-ef0592cee0b3); Time taken: 0.067 seconds
INFO  : Executing command(queryId=hive_20170511041717_8ab7b9a9-87d4-492d-816b-ef0592cee0b3): GRANT ROLE sentry_admin TO GROUP root
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041717_8ab7b9a9-87d4-492d-816b-ef0592cee0b3); Time taken: 0.1 seconds
INFO  : OK
No rows affected (0.184 seconds)
0: jdbc:hive2://localhost:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20170511041717_a82a9fc0-4a88-47f5-9f1a-4eba5d50f206): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170511041717_a82a9fc0-4a88-47f5-9f1a-4eba5d50f206); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20170511041717_a82a9fc0-4a88-47f5-9f1a-4eba5d50f206): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511041717_a82a9fc0-4a88-47f5-9f1a-4eba5d50f206); Time taken: 0.147 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.285 seconds)


[root@ip-172-31-41-53 hue]# groupadd selector
[root@ip-172-31-41-53 hue]# groupadd inserters
[root@ip-172-31-41-53 hue]# useradd -u 1100 -g selector george
[root@ip-172-31-41-53 hue]# useradd -u 1200 -g inserters ferdinand

[root@ip-172-31-41-53 hue]# kadmin.local -q "add_principal george"
Authenticating as principal root/admin@SWAYTEC.COM with password.
WARNING: no policy specified for george@SWAYTEC.COM; defaulting to no policy
Enter password for principal "george@SWAYTEC.COM": 
Re-enter password for principal "george@SWAYTEC.COM": 
Principal "george@SWAYTEC.COM" created.

[root@ip-172-31-41-53 hue]# kadmin.local -q "add_principal ferdinand"
Authenticating as principal root/admin@SWAYTEC.COM with password.
WARNING: no policy specified for ferdinand@SWAYTEC.COM; defaulting to no policy
Enter password for principal "ferdinand@SWAYTEC.COM": 
Re-enter password for principal "ferdinand@SWAYTEC.COM": 
Principal "ferdinand@SWAYTEC.COM" created.






0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20170511042525_23fabfee-7e71-4cd1-b84c-3c95d0b384f4): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042525_23fabfee-7e71-4cd1-b84c-3c95d0b384f4); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20170511042525_23fabfee-7e71-4cd1-b84c-3c95d0b384f4): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042525_23fabfee-7e71-4cd1-b84c-3c95d0b384f4); Time taken: 0.054 seconds
INFO  : OK
No rows affected (0.195 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20170511042525_2fed942e-961a-4ecf-8186-6ee5173c5df3): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042525_2fed942e-961a-4ecf-8186-6ee5173c5df3); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20170511042525_2fed942e-961a-4ecf-8186-6ee5173c5df3): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042525_2fed942e-961a-4ecf-8186-6ee5173c5df3); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.109 seconds)
0: jdbc:hive2://localhost:10000/default> 
0: jdbc:hive2://localhost:10000/default> 
0: jdbc:hive2://localhost:10000/default> 
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20170511042727_29c6dc4d-d756-44df-a4e0-c51bb24bdf64): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042727_29c6dc4d-d756-44df-a4e0-c51bb24bdf64); Time taken: 0.097 seconds
INFO  : Executing command(queryId=hive_20170511042727_29c6dc4d-d756-44df-a4e0-c51bb24bdf64): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042727_29c6dc4d-d756-44df-a4e0-c51bb24bdf64); Time taken: 0.038 seconds
INFO  : OK
No rows affected (0.153 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20170511042727_ca1d55a8-39da-4d1a-ac83-8a4641c3202b): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20170511042727_ca1d55a8-39da-4d1a-ac83-8a4641c3202b); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20170511042727_ca1d55a8-39da-4d1a-ac83-8a4641c3202b): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170511042727_ca1d55a8-39da-4d1a-ac83-8a4641c3202b); Time taken: 0.039 seconds
INFO  : OK
No rows affected (0.114 seconds)







[root@ip-172-31-41-53 hue]# kinit george
Password for george@SWAYTEC.COM: 
[root@ip-172-31-41-53 hue]# 
[root@ip-172-31-41-53 hue]# 
[root@ip-172-31-41-53 hue]# 
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





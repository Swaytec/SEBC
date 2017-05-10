## Create a precious directory in HDFS; copy the ZIP course file into it.
```
[hdfs@ip-172-31-42-246 hadoop-0.20-mapreduce]$ hdfs dfs -mkdir /precious
[hdfs@ip-172-31-42-246 hadoop-0.20-mapreduce]$ hdfs dfs -ls /
Found 5 items
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 03:36 /Data500m
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 08:00 /precious
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 06:16 /replicdata
drwxrwxrwt   - hdfs supergroup          0 2017-05-09 05:46 /tmp
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 06:54 /user

[hdfs@ip-172-31-42-246 tmp]$ hadoop fs -put /tmp/SEBC-Shanghai.zip /precious
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     474957 2017-05-09 08:17 /precious/SEBC-Shanghai.zip
```


## Delete the directory
```
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -rm -r /precious
rm: Failed to move to trash: hdfs://ip-172-31-42-246.us-west-2.compute.internal:8020/precious: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots
```

## Delete the ZIP file
```
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -rm  /precious/SEBC-Shanghai.zip
17/05/09 08:31:04 INFO fs.TrashPolicyDefault: Moved: 'hdfs://ip-172-31-42-246.us-west-2.compute.internal:8020/precious/SEBC-Shanghai.zip' to trash at: hdfs://ip-172-31-42-246.us-west-2.compute.internal:8020/user/hdfs/.Trash/Current/precious/SEBC-Shanghai.zip
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -ls /precious
```

## Restore the deleted file
```
hdfs dfs -ls -R /precious/.snapshot
hdfs dfs -cp /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /precious
```


Use teragen to create a 500 MB file

```
[hdfs@ip-172-31-42-246 jars]$ hadoop jar hadoop-examples.jar teragen 5000000 /Data500m/
17/05/09 03:36:25 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-42-246.us-west-2.compute.internal/172.31.42.246:8032
17/05/09 03:36:26 INFO terasort.TeraSort: Generating 5000000 using 2
17/05/09 03:36:26 INFO mapreduce.JobSubmitter: number of splits:2
17/05/09 03:36:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494257759444_0004
17/05/09 03:36:27 INFO impl.YarnClientImpl: Submitted application application_1494257759444_0004
17/05/09 03:36:27 INFO mapreduce.Job: The url to track the job: http://ip-172-31-42-246.us-west-2.compute.internal:8088/proxy/application_1494257759444_0004/
17/05/09 03:36:27 INFO mapreduce.Job: Running job: job_1494257759444_0004
17/05/09 03:36:33 INFO mapreduce.Job: Job job_1494257759444_0004 running in uber mode : false
17/05/09 03:36:33 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 03:36:45 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 03:36:45 INFO mapreduce.Job: Job job_1494257759444_0004 completed successfully
17/05/09 03:36:45 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=245490
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=167
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=4
        Job Counters 
                Launched map tasks=2
                Other local map tasks=2
                Total time spent by all maps in occupied slots (ms)=19313
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=19313
                Total vcore-seconds taken by all map tasks=19313
                Total megabyte-seconds taken by all map tasks=19776512
        Map-Reduce Framework
                Map input records=5000000
                Map output records=5000000
                Input split bytes=167
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=223
                CPU time spent (ms)=15290
                Physical memory (bytes) snapshot=716230656
                Virtual memory (bytes) snapshot=5546962944
                Total committed heap usage (bytes)=723517440
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=10735710707299981
        File Input Format Counters                                                                                             Bytes Read=0                                                                                           File Output Format Counters 
                Bytes Written=500000000
[hdfs@ip-172-31-42-246 jars]$ hdfs dfs -ls /
Found 3 items
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 03:36 /Data500m
drwxrwxrwt   - hdfs supergroup          0 2017-05-08 15:35 /tmp
drwxr-xr-x   - hdfs supergroup          0 2017-05-09 03:20 /user
[hdfs@ip-172-31-42-246 jars]$ hdfs dfs -du -h /Data500m/
0        0        /Data500m/_SUCCESS
238.4 M  715.3 M  /Data500m/part-m-00000
238.4 M  715.3 M  /Data500m/part-m-00001
```


Copy your partner's file to your target directory
```
I had test distcp to partner cluster,because network zone limit different zone private ip doesn't connect each other in aws,so I just test command below
(Note:if config host map private ip to public ip, can be resolve this question,i have already proof this with partner student)
change all node host file
34.208.80.199 ip-172-31-37-12.us-west-2.compute.internal
35.161.179.128 ip-172-31-37-146.us-west-2.compute.internal
52.40.130.144 ip-172-31-41-227.us-west-2.compute.internal



[hdfs@ip-172-31-42-246 tmp]$ hadoop distcp hdfs://ec2-35-163-39-218.us-west-2.compute.amazonaws.com:8020/Data500m hdfs://ec2-172-31-42-246.us-west-2.compute.amazonaws.com:8020/replicdata
17/05/09 06:16:23 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[hdfs://ec2-35-163-39-218.us-west-2.compute.amazonaws.com:8020/Data500m], targetPath=hdfs://ec2-172-31-42-246.us-west-2.compute.amazonaws.com:8020/replicdata, targetPathExists=false, filtersFile='null'}
17/05/09 06:16:23 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-42-246.us-west-2.compute.internal/172.31.42.246:8032
17/05/09 06:16:23 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 4; dirCnt = 1
17/05/09 06:16:23 INFO tools.SimpleCopyListing: Build file listing completed.
17/05/09 06:16:23 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/05/09 06:16:23 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/05/09 06:16:23 INFO tools.DistCp: Number of paths in the copy list: 4
17/05/09 06:16:23 INFO tools.DistCp: Number of paths in the copy list: 4
17/05/09 06:16:23 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-42-246.us-west-2.compute.internal/172.31.42.246:8032
17/05/09 06:16:24 INFO mapreduce.JobSubmitter: number of splits:3
17/05/09 06:16:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494257759444_0015
17/05/09 06:16:24 INFO impl.YarnClientImpl: Submitted application application_1494257759444_0015
17/05/09 06:16:24 INFO mapreduce.Job: The url to track the job: http://ip-172-31-42-246.us-west-2.compute.internal:8088/proxy/application_1494257759444_0015/
17/05/09 06:16:24 INFO tools.DistCp: DistCp job-id: job_1494257759444_0015
17/05/09 06:16:24 INFO mapreduce.Job: Running job: job_1494257759444_0015
17/05/09 06:16:31 INFO mapreduce.Job: Job job_1494257759444_0015 running in uber mode : false
17/05/09 06:16:31 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 06:16:37 INFO mapreduce.Job:  map 33% reduce 0%
17/05/09 06:16:40 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 06:16:41 INFO mapreduce.Job: Job job_1494257759444_0015 completed successfully
17/05/09 06:16:41 INFO mapreduce.Job: Counters: 33
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=376980
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=500001747
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=56
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=13
        Job Counters 
                Launched map tasks=3
                Other local map tasks=3
                Total time spent by all maps in occupied slots (ms)=19402
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=19402
                Total vcore-seconds taken by all map tasks=19402
                Total megabyte-seconds taken by all map tasks=19867648
        Map-Reduce Framework
                Map input records=4
                Map output records=0
                Input split bytes=345
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=242
                CPU time spent (ms)=13510
                Physical memory (bytes) snapshot=761761792
                Virtual memory (bytes) snapshot=8417304576
                Total committed heap usage (bytes)=706740224
        File Input Format Counters 
                Bytes Read=1402
        File Output Format Counters 
                Bytes Written=0
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=500000000
                BYTESEXPECTED=500000000
                COPY=4


[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -ls /replicdata
Found 3 items
-rw-r--r--   3 hdfs supergroup          0 2017-05-09 06:16 /replicdata/_SUCCESS
-rw-r--r--   3 hdfs supergroup  250000000 2017-05-09 06:16 /replicdata/part-m-00000
-rw-r--r--   3 hdfs supergroup  250000000 2017-05-09 06:16 /replicdata/part-m-00001

```




Browse the results
```
[hdfs@ip-172-31-42-246 jars]$ hdfs fsck /Data500m -files -blocks
Connecting to namenode via http://ip-172-31-42-246.us-west-2.compute.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.42.246 for path /Data500m at Tue May 09 03:39:32 UTC 2017
/Data500m <dir>
/Data500m/_SUCCESS 0 bytes, 0 block(s):  OK

/Data500m/part-m-00000 250000000 bytes, 2 block(s):  OK
0. BP-1193531456-172.31.42.246-1494257693726:blk_1073742568_1744 len=134217728 Live_repl=3
1. BP-1193531456-172.31.42.246-1494257693726:blk_1073742570_1746 len=115782272 Live_repl=3

/Data500m/part-m-00001 250000000 bytes, 2 block(s):  OK
0. BP-1193531456-172.31.42.246-1494257693726:blk_1073742569_1745 len=134217728 Live_repl=3
1. BP-1193531456-172.31.42.246-1494257693726:blk_1073742571_1747 len=115782272 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    1
 Total files:   3
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          4
 Number of racks:               1
FSCK ended at Tue May 09 03:39:32 UTC 2017 in 2 milliseconds


The filesystem under path '/Data500m' is HEALTHY
```


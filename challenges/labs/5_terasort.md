## zhou run terasort script with kerberos

```
[zhou@ip-172-31-43-169 root]$ kinit zhou
[zhou@ip-172-31-43-169 root]$ klist -e
Ticket cache: FILE:/tmp/krb5cc_2800
Default principal: zhou@SWAYTEC.CN

Valid starting     Expires            Service principal
05/12/17 03:20:32  05/13/17 03:20:32  krbtgt/SWAYTEC.CN@SWAYTEC.CN
        renew until 05/19/17 03:20:32, Etype (skey, tkt): arcfour-hmac, arcfour-hmac 

[zhou@ip-172-31-43-169 root]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=6 -D dfs.blocksize=64m -Dmapreduce.map.memory.mb=1024 65536000 tsort
17/05/12 03:24:04 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-43-169.us-west-2.compute.internal/172.31.43.169:8032
17/05/12 03:24:05 INFO hdfs.DFSClient: Created token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494559444979, maxDate=1495164244979, sequenceNumber=2, masterKeyId=2 on 172.31.43.169:8020
17/05/12 03:24:05 INFO security.TokenCache: Got dt for hdfs://ip-172-31-43-169.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.43.169:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494559444979, maxDate=1495164244979, sequenceNumber=2, masterKeyId=2)
17/05/12 03:24:05 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 03:24:05 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 03:24:05 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/12 03:24:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494558877043_0002
17/05/12 03:24:05 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.43.169:8020, Ident: (token for zhou: HDFS_DELEGATION_TOKEN owner=zhou@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494559444979, maxDate=1495164244979, sequenceNumber=2, masterKeyId=2)
17/05/12 03:24:06 INFO impl.YarnClientImpl: Submitted application application_1494558877043_0002
17/05/12 03:24:06 INFO mapreduce.Job: The url to track the job: http://ip-172-31-43-169.us-west-2.compute.internal:8088/proxy/application_1494558877043_0002/
17/05/12 03:24:06 INFO mapreduce.Job: Running job: job_1494558877043_0002
17/05/12 03:24:15 INFO mapreduce.Job: Job job_1494558877043_0002 running in uber mode : false
17/05/12 03:24:15 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 03:24:28 INFO mapreduce.Job:  map 8% reduce 0%
17/05/12 03:24:31 INFO mapreduce.Job:  map 12% reduce 0%
17/05/12 03:24:32 INFO mapreduce.Job:  map 19% reduce 0%
17/05/12 03:24:33 INFO mapreduce.Job:  map 25% reduce 0%
17/05/12 03:24:34 INFO mapreduce.Job:  map 27% reduce 0%
17/05/12 03:24:35 INFO mapreduce.Job:  map 29% reduce 0%
17/05/12 03:24:36 INFO mapreduce.Job:  map 31% reduce 0%
17/05/12 03:24:37 INFO mapreduce.Job:  map 33% reduce 0%
17/05/12 03:24:38 INFO mapreduce.Job:  map 34% reduce 0%
17/05/12 03:24:39 INFO mapreduce.Job:  map 35% reduce 0%
17/05/12 03:24:40 INFO mapreduce.Job:  map 38% reduce 0%
17/05/12 03:24:42 INFO mapreduce.Job:  map 39% reduce 0%
17/05/12 03:24:43 INFO mapreduce.Job:  map 42% reduce 0%
17/05/12 03:24:44 INFO mapreduce.Job:  map 43% reduce 0%
17/05/12 03:24:45 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 03:24:46 INFO mapreduce.Job:  map 46% reduce 0%
17/05/12 03:24:47 INFO mapreduce.Job:  map 48% reduce 0%
17/05/12 03:24:48 INFO mapreduce.Job:  map 49% reduce 0%
17/05/12 03:24:50 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 03:24:52 INFO mapreduce.Job:  map 53% reduce 0%
17/05/12 03:24:53 INFO mapreduce.Job:  map 57% reduce 0%
17/05/12 03:24:55 INFO mapreduce.Job:  map 58% reduce 0%
17/05/12 03:24:56 INFO mapreduce.Job:  map 62% reduce 0%
17/05/12 03:24:58 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 03:24:59 INFO mapreduce.Job:  map 66% reduce 0%
17/05/12 03:25:01 INFO mapreduce.Job:  map 67% reduce 0%
17/05/12 03:25:02 INFO mapreduce.Job:  map 69% reduce 0%
17/05/12 03:25:04 INFO mapreduce.Job:  map 71% reduce 0%
17/05/12 03:25:05 INFO mapreduce.Job:  map 73% reduce 0%
17/05/12 03:25:07 INFO mapreduce.Job:  map 76% reduce 0%
17/05/12 03:25:08 INFO mapreduce.Job:  map 78% reduce 0%
17/05/12 03:25:10 INFO mapreduce.Job:  map 81% reduce 0%
17/05/12 03:25:11 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 03:25:13 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 03:25:14 INFO mapreduce.Job:  map 86% reduce 0%
17/05/12 03:25:16 INFO mapreduce.Job:  map 88% reduce 0%
17/05/12 03:25:17 INFO mapreduce.Job:  map 90% reduce 0%
17/05/12 03:25:19 INFO mapreduce.Job:  map 92% reduce 0%
17/05/12 03:25:20 INFO mapreduce.Job:  map 94% reduce 0%
17/05/12 03:25:22 INFO mapreduce.Job:  map 96% reduce 0%
17/05/12 03:25:25 INFO mapreduce.Job:  map 99% reduce 0%
17/05/12 03:25:26 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 03:25:26 INFO mapreduce.Job: Job job_1494558877043_0002 completed successfully
17/05/12 03:25:26 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=745632
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=511
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=24
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters 
                Launched map tasks=6
                Other local map tasks=6
                Total time spent by all maps in occupied slots (ms)=379271
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=379271
                Total vcore-seconds taken by all map tasks=379271
                Total megabyte-seconds taken by all map tasks=388373504
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=511
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1189
                CPU time spent (ms)=123050
                Physical memory (bytes) snapshot=1982472192
                Virtual memory (bytes) snapshot=9339498496
                Total committed heap usage (bytes)=1984430080
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters 
                Bytes Read=0
        File Output Format Counters 
                Bytes Written=6553600000

real    1m25.112s
user    0m6.245s
sys     0m0.739s

```
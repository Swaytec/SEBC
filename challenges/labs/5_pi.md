## chen run pi script with kerberos
```
[chen@ip-172-31-43-169 root]$ kinit chen
[chen@ip-172-31-43-169 root]$ klist -e
Ticket cache: FILE:/tmp/krb5cc_2900
Default principal: chen@SWAYTEC.CN

Valid starting     Expires            Service principal
05/12/17 03:38:40  05/13/17 03:38:40  krbtgt/SWAYTEC.CN@SWAYTEC.CN
        renew until 05/19/17 03:38:40, Etype (skey, tkt): arcfour-hmac, arcfour-hmac 

[chen@ip-172-31-43-169 root]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 10 10
Number of Maps  = 10
Samples per Map = 10
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Starting Job
17/05/12 03:39:34 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-43-169.us-west-2.compute.internal/172.31.43.169:8032
17/05/12 03:39:34 INFO hdfs.DFSClient: Created token for chen: HDFS_DELEGATION_TOKEN owner=chen@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494560374876, maxDate=1495165174876, sequenceNumber=3, masterKeyId=2 on 172.31.43.169:8020
17/05/12 03:39:34 INFO security.TokenCache: Got dt for hdfs://ip-172-31-43-169.us-west-2.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.43.169:8020, Ident: (token for chen: HDFS_DELEGATION_TOKEN owner=chen@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494560374876, maxDate=1495165174876, sequenceNumber=3, masterKeyId=2)
17/05/12 03:39:35 INFO input.FileInputFormat: Total input paths to process : 10
17/05/12 03:39:35 INFO mapreduce.JobSubmitter: number of splits:10
17/05/12 03:39:35 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494558877043_0003
17/05/12 03:39:35 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.43.169:8020, Ident: (token for chen: HDFS_DELEGATION_TOKEN owner=chen@SWAYTEC.CN, renewer=yarn, realUser=, issueDate=1494560374876, maxDate=1495165174876, sequenceNumber=3, masterKeyId=2)
17/05/12 03:39:35 INFO impl.YarnClientImpl: Submitted application application_1494558877043_0003
17/05/12 03:39:35 INFO mapreduce.Job: The url to track the job: http://ip-172-31-43-169.us-west-2.compute.internal:8088/proxy/application_1494558877043_0003/
17/05/12 03:39:35 INFO mapreduce.Job: Running job: job_1494558877043_0003
17/05/12 03:39:45 INFO mapreduce.Job: Job job_1494558877043_0003 running in uber mode : false
17/05/12 03:39:45 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 03:39:53 INFO mapreduce.Job:  map 20% reduce 0%
17/05/12 03:39:56 INFO mapreduce.Job:  map 40% reduce 0%
17/05/12 03:39:59 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 03:40:06 INFO mapreduce.Job:  map 100% reduce 100%
17/05/12 03:40:06 INFO mapreduce.Job: Job job_1494558877043_0003 completed successfully
17/05/12 03:40:06 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=77
                FILE: Number of bytes written=1374998
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=2980
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=43
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters 
                Launched map tasks=10
                Launched reduce tasks=1
                Data-local map tasks=10
                Total time spent by all maps in occupied slots (ms)=101917
                Total time spent by all reduces in occupied slots (ms)=4076
                Total time spent by all map tasks (ms)=101917
                Total time spent by all reduce tasks (ms)=4076
                Total vcore-seconds taken by all map tasks=101917
                Total vcore-seconds taken by all reduce tasks=4076
                Total megabyte-seconds taken by all map tasks=104363008
                Total megabyte-seconds taken by all reduce tasks=4173824
        Map-Reduce Framework
                Map input records=10
                Map output records=20
                Map output bytes=180
                Map output materialized bytes=339
                Input split bytes=1800
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=339
                Reduce input records=20
                Reduce output records=0
                Spilled Records=40
                Shuffled Maps =10
                Failed Shuffles=0
                Merged Map outputs=10
                GC time elapsed (ms)=415
                CPU time spent (ms)=9260
                Physical memory (bytes) snapshot=4682067968
                Virtual memory (bytes) snapshot=17218404352
                Total committed heap usage (bytes)=5534384128
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters 
                Bytes Read=1180
        File Output Format Counters 
                Bytes Written=97
Job Finished in 31.769 seconds
Estimated value of Pi is 3.20000000000000000000

```
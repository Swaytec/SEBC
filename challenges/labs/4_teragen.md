## full teragen command 
```
[zhou@ip-172-31-43-169 cloudera-scm-server]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=6 -D dfs.blocksize=64m -Dmapreduce.map.memory.mb=1024 65536000 tgen
```

## run output
```
[zhou@ip-172-31-43-169 cloudera-scm-server]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=6 -D dfs.blocksize=64m -Dmapreduce.map.memory.mb=1024 65536000 tgen
17/05/12 02:36:26 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-43-169.us-west-2.compute.internal/172.31.43.169:8032
17/05/12 02:36:26 INFO terasort.TeraSort: Generating 65536000 using 6
17/05/12 02:36:26 INFO mapreduce.JobSubmitter: number of splits:6
17/05/12 02:36:26 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/12 02:36:27 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494554501914_0004
17/05/12 02:36:27 INFO impl.YarnClientImpl: Submitted application application_1494554501914_0004
17/05/12 02:36:27 INFO mapreduce.Job: The url to track the job: http://ip-172-31-43-169.us-west-2.compute.internal:8088/proxy/application_1494554501914_0004/
17/05/12 02:36:27 INFO mapreduce.Job: Running job: job_1494554501914_0004
17/05/12 02:36:33 INFO mapreduce.Job: Job job_1494554501914_0004 running in uber mode : false
17/05/12 02:36:33 INFO mapreduce.Job:  map 0% reduce 0%
17/05/12 02:36:46 INFO mapreduce.Job:  map 11% reduce 0%
17/05/12 02:36:47 INFO mapreduce.Job:  map 17% reduce 0%
17/05/12 02:36:49 INFO mapreduce.Job:  map 23% reduce 0%
17/05/12 02:36:50 INFO mapreduce.Job:  map 26% reduce 0%
17/05/12 02:36:52 INFO mapreduce.Job:  map 28% reduce 0%
17/05/12 02:36:53 INFO mapreduce.Job:  map 29% reduce 0%
17/05/12 02:36:55 INFO mapreduce.Job:  map 32% reduce 0%
17/05/12 02:36:56 INFO mapreduce.Job:  map 34% reduce 0%
17/05/12 02:36:58 INFO mapreduce.Job:  map 36% reduce 0%
17/05/12 02:36:59 INFO mapreduce.Job:  map 37% reduce 0%
17/05/12 02:37:02 INFO mapreduce.Job:  map 40% reduce 0%
17/05/12 02:37:03 INFO mapreduce.Job:  map 41% reduce 0%
17/05/12 02:37:05 INFO mapreduce.Job:  map 44% reduce 0%
17/05/12 02:37:08 INFO mapreduce.Job:  map 48% reduce 0%
17/05/12 02:37:11 INFO mapreduce.Job:  map 52% reduce 0%
17/05/12 02:37:14 INFO mapreduce.Job:  map 58% reduce 0%
17/05/12 02:37:17 INFO mapreduce.Job:  map 63% reduce 0%
17/05/12 02:37:19 INFO mapreduce.Job:  map 64% reduce 0%
17/05/12 02:37:20 INFO mapreduce.Job:  map 68% reduce 0%
17/05/12 02:37:23 INFO mapreduce.Job:  map 72% reduce 0%
17/05/12 02:37:25 INFO mapreduce.Job:  map 73% reduce 0%
17/05/12 02:37:26 INFO mapreduce.Job:  map 76% reduce 0%
17/05/12 02:37:28 INFO mapreduce.Job:  map 77% reduce 0%
17/05/12 02:37:29 INFO mapreduce.Job:  map 81% reduce 0%
17/05/12 02:37:31 INFO mapreduce.Job:  map 82% reduce 0%
17/05/12 02:37:32 INFO mapreduce.Job:  map 85% reduce 0%
17/05/12 02:37:34 INFO mapreduce.Job:  map 87% reduce 0%
17/05/12 02:37:35 INFO mapreduce.Job:  map 88% reduce 0%
17/05/12 02:37:38 INFO mapreduce.Job:  map 90% reduce 0%
17/05/12 02:37:39 INFO mapreduce.Job:  map 91% reduce 0%
17/05/12 02:37:41 INFO mapreduce.Job:  map 93% reduce 0%
17/05/12 02:37:42 INFO mapreduce.Job:  map 94% reduce 0%
17/05/12 02:37:44 INFO mapreduce.Job:  map 96% reduce 0%
17/05/12 02:37:45 INFO mapreduce.Job:  map 97% reduce 0%
17/05/12 02:37:47 INFO mapreduce.Job:  map 100% reduce 0%
17/05/12 02:37:47 INFO mapreduce.Job: Job job_1494554501914_0004 completed successfully
17/05/12 02:37:47 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=741168
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
                Total time spent by all maps in occupied slots (ms)=397723
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=397723
                Total vcore-seconds taken by all map tasks=397723
                Total megabyte-seconds taken by all map tasks=407268352
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=511
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1206
                CPU time spent (ms)=125100
                Physical memory (bytes) snapshot=1987006464
                Virtual memory (bytes) snapshot=9391099904
                Total committed heap usage (bytes)=1978662912
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters 
                Bytes Read=0
        File Output Format Counters 
                Bytes Written=6553600000

real    1m24.011s
user    0m5.987s
sys     0m0.782s
```

## list /user/zhou/tgen
```
[zhou@ip-172-31-43-169 cloudera-scm-server]$ hdfs dfs -ls /user/zhou/tgen
Found 7 items
-rw-r--r--   3 zhou supergroup          0 2017-05-12 02:37 /user/zhou/tgen/_SUCCESS
-rw-r--r--   3 zhou supergroup 1092266700 2017-05-12 02:37 /user/zhou/tgen/part-m-00000
-rw-r--r--   3 zhou supergroup 1092266700 2017-05-12 02:37 /user/zhou/tgen/part-m-00001
-rw-r--r--   3 zhou supergroup 1092266600 2017-05-12 02:37 /user/zhou/tgen/part-m-00002
-rw-r--r--   3 zhou supergroup 1092266700 2017-05-12 02:37 /user/zhou/tgen/part-m-00003
-rw-r--r--   3 zhou supergroup 1092266700 2017-05-12 02:37 /user/zhou/tgen/part-m-00004
-rw-r--r--   3 zhou supergroup 1092266600 2017-05-12 02:37 /user/zhou/tgen/part-m-00005

```
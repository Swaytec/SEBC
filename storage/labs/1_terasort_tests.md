
Create an end-user Linux account named with your GitHub handle
```
[hdfs@ip-172-31-42-246 tmp]$ useradd swaytec
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -mkdir /user/swaytec
[hdfs@ip-172-31-42-246 tmp]$ hdfs dfs -chown swaytec /user/swaytec
[root@ip-172-31-42-246 tmp]# su swaytec
```

Create a 10 GB file using teragen
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.map.tasks=4 -D dfs.blocksize=32m -Dmapred.map.tasks.speculative.execution=false 100000000 /user/swaytec/Data10G


17/05/09 07:35:37 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-42-246.us-west-2.compute.internal/172.31.42.246:8032
17/05/09 07:35:38 INFO terasort.TeraSort: Generating 100000000 using 4
17/05/09 07:35:38 INFO mapreduce.JobSubmitter: number of splits:4
17/05/09 07:35:38 INFO Configuration.deprecation: mapred.map.tasks.speculative.execution is deprecated. Instead, use mapreduce.map.speculative
17/05/09 07:35:38 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
17/05/09 07:35:38 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1494257759444_0016
17/05/09 07:35:38 INFO impl.YarnClientImpl: Submitted application application_1494257759444_0016
17/05/09 07:35:38 INFO mapreduce.Job: The url to track the job: http://ip-172-31-42-246.us-west-2.compute.internal:8088/proxy/application_1494257759444_0016/
17/05/09 07:35:38 INFO mapreduce.Job: Running job: job_1494257759444_0016
17/05/09 07:35:45 INFO mapreduce.Job: Job job_1494257759444_0016 running in uber mode : false
17/05/09 07:35:45 INFO mapreduce.Job:  map 0% reduce 0%
17/05/09 07:35:55 INFO mapreduce.Job:  map 4% reduce 0%
17/05/09 07:35:58 INFO mapreduce.Job:  map 9% reduce 0%
17/05/09 07:35:59 INFO mapreduce.Job:  map 11% reduce 0%
17/05/09 07:36:01 INFO mapreduce.Job:  map 15% reduce 0%
17/05/09 07:36:02 INFO mapreduce.Job:  map 16% reduce 0%
17/05/09 07:36:04 INFO mapreduce.Job:  map 18% reduce 0%
17/05/09 07:36:05 INFO mapreduce.Job:  map 20% reduce 0%
17/05/09 07:36:07 INFO mapreduce.Job:  map 21% reduce 0%
17/05/09 07:36:08 INFO mapreduce.Job:  map 22% reduce 0%
17/05/09 07:36:10 INFO mapreduce.Job:  map 23% reduce 0%
17/05/09 07:36:11 INFO mapreduce.Job:  map 24% reduce 0%
17/05/09 07:36:13 INFO mapreduce.Job:  map 25% reduce 0%
17/05/09 07:36:14 INFO mapreduce.Job:  map 26% reduce 0%
17/05/09 07:36:16 INFO mapreduce.Job:  map 28% reduce 0%
17/05/09 07:36:17 INFO mapreduce.Job:  map 29% reduce 0%
17/05/09 07:36:19 INFO mapreduce.Job:  map 30% reduce 0%
17/05/09 07:36:20 INFO mapreduce.Job:  map 31% reduce 0%
17/05/09 07:36:22 INFO mapreduce.Job:  map 33% reduce 0%
17/05/09 07:36:23 INFO mapreduce.Job:  map 34% reduce 0%
17/05/09 07:36:25 INFO mapreduce.Job:  map 36% reduce 0%
17/05/09 07:36:26 INFO mapreduce.Job:  map 37% reduce 0%
17/05/09 07:36:28 INFO mapreduce.Job:  map 38% reduce 0%
17/05/09 07:36:29 INFO mapreduce.Job:  map 39% reduce 0%
17/05/09 07:36:31 INFO mapreduce.Job:  map 41% reduce 0%
17/05/09 07:36:32 INFO mapreduce.Job:  map 42% reduce 0%
17/05/09 07:36:34 INFO mapreduce.Job:  map 43% reduce 0%
17/05/09 07:36:35 INFO mapreduce.Job:  map 44% reduce 0%
17/05/09 07:36:37 INFO mapreduce.Job:  map 45% reduce 0%
17/05/09 07:36:38 INFO mapreduce.Job:  map 46% reduce 0%
17/05/09 07:36:40 INFO mapreduce.Job:  map 48% reduce 0%
17/05/09 07:36:41 INFO mapreduce.Job:  map 49% reduce 0%
17/05/09 07:36:43 INFO mapreduce.Job:  map 50% reduce 0%
17/05/09 07:36:44 INFO mapreduce.Job:  map 51% reduce 0%
17/05/09 07:36:46 INFO mapreduce.Job:  map 52% reduce 0%
17/05/09 07:36:47 INFO mapreduce.Job:  map 53% reduce 0%
17/05/09 07:36:49 INFO mapreduce.Job:  map 54% reduce 0%
17/05/09 07:36:50 INFO mapreduce.Job:  map 55% reduce 0%
17/05/09 07:36:52 INFO mapreduce.Job:  map 57% reduce 0%
17/05/09 07:36:53 INFO mapreduce.Job:  map 58% reduce 0%
17/05/09 07:36:55 INFO mapreduce.Job:  map 59% reduce 0%
17/05/09 07:36:56 INFO mapreduce.Job:  map 60% reduce 0%
17/05/09 07:36:58 INFO mapreduce.Job:  map 62% reduce 0%
17/05/09 07:36:59 INFO mapreduce.Job:  map 63% reduce 0%
17/05/09 07:37:01 INFO mapreduce.Job:  map 64% reduce 0%
17/05/09 07:37:02 INFO mapreduce.Job:  map 65% reduce 0%
17/05/09 07:37:04 INFO mapreduce.Job:  map 66% reduce 0%
17/05/09 07:37:05 INFO mapreduce.Job:  map 67% reduce 0%
17/05/09 07:37:07 INFO mapreduce.Job:  map 68% reduce 0%
17/05/09 07:37:08 INFO mapreduce.Job:  map 69% reduce 0%
17/05/09 07:37:10 INFO mapreduce.Job:  map 70% reduce 0%
17/05/09 07:37:11 INFO mapreduce.Job:  map 71% reduce 0%
17/05/09 07:37:13 INFO mapreduce.Job:  map 72% reduce 0%
17/05/09 07:37:14 INFO mapreduce.Job:  map 73% reduce 0%
17/05/09 07:37:16 INFO mapreduce.Job:  map 75% reduce 0%
17/05/09 07:37:17 INFO mapreduce.Job:  map 76% reduce 0%
17/05/09 07:37:19 INFO mapreduce.Job:  map 77% reduce 0%
17/05/09 07:37:20 INFO mapreduce.Job:  map 78% reduce 0%
17/05/09 07:37:23 INFO mapreduce.Job:  map 80% reduce 0%
17/05/09 07:37:26 INFO mapreduce.Job:  map 81% reduce 0%
17/05/09 07:37:28 INFO mapreduce.Job:  map 82% reduce 0%
17/05/09 07:37:29 INFO mapreduce.Job:  map 83% reduce 0%
17/05/09 07:37:31 INFO mapreduce.Job:  map 84% reduce 0%
17/05/09 07:37:32 INFO mapreduce.Job:  map 85% reduce 0%
17/05/09 07:37:34 INFO mapreduce.Job:  map 86% reduce 0%
17/05/09 07:37:35 INFO mapreduce.Job:  map 87% reduce 0%
17/05/09 07:37:38 INFO mapreduce.Job:  map 89% reduce 0%
17/05/09 07:37:41 INFO mapreduce.Job:  map 91% reduce 0%
17/05/09 07:37:44 INFO mapreduce.Job:  map 92% reduce 0%
17/05/09 07:37:47 INFO mapreduce.Job:  map 94% reduce 0%
17/05/09 07:37:50 INFO mapreduce.Job:  map 96% reduce 0%
17/05/09 07:37:53 INFO mapreduce.Job:  map 98% reduce 0%
17/05/09 07:37:56 INFO mapreduce.Job:  map 100% reduce 0%
17/05/09 07:37:57 INFO mapreduce.Job: Job job_1494257759444_0016 completed successfully
17/05/09 07:37:58 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=491108
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10000000000
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters 
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=480134
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=480134
                Total vcore-seconds taken by all map tasks=480134
                Total megabyte-seconds taken by all map tasks=491657216
        Map-Reduce Framework
                Map input records=100000000
                Map output records=100000000
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=959
                CPU time spent (ms)=154950
                Physical memory (bytes) snapshot=1441959936
                Virtual memory (bytes) snapshot=11111096320
                Total committed heap usage (bytes)=1063256064
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=214760662691937609
        File Input Format Counters 
                Bytes Read=0
        File Output Format Counters 
                Bytes Written=10000000000

real    2m23.141s
user    0m7.587s
sys     0m0.898s

[swaytec@ip-172-31-42-246 hadoop-0.20-mapreduce]$ hdfs dfs -du -h /user/swaytec/Data10G
0      0      /user/swaytec/Data10G/_SUCCESS
2.3 G  7.0 G  /user/swaytec/Data10G/part-m-00000
2.3 G  7.0 G  /user/swaytec/Data10G/part-m-00001
2.3 G  7.0 G  /user/swaytec/Data10G/part-m-00002
2.3 G  7.0 G  /user/swaytec/Data10G/part-m-00003

```

Run the terasort command on this file
```
time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapred.map.tasks.speculative.execution=false /user/swaytec/Data10G terasort_out

real    5m32.414s
user    0m10.112s
sys     0m1.146s
```




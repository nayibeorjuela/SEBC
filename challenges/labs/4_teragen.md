// Teragen
[root@ip-172-31-35-119 centos]# sudo -u saturn time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=12 -Dmapreduce.map.memory.mb=32 -Dmapreduce.map.java.opts.max.heap=512 65536000 /user/saturn/tgen
17/07/21 19:27:59 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-46-220.us-west-2.compute.internal/172.31.46.220:8032
17/07/21 19:28:00 INFO terasort.TeraGen: Generating 65536000 using 12
17/07/21 19:28:00 INFO mapreduce.JobSubmitter: number of splits:12
17/07/21 19:28:00 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1500661353002_0001
17/07/21 19:28:00 INFO impl.YarnClientImpl: Submitted application application_1500661353002_0001
17/07/21 19:28:01 INFO mapreduce.Job: The url to track the job: http://ip-172-31-46-220.us-west-2.compute.internal:8088/proxy/application_1500661353002_0001/
17/07/21 19:28:01 INFO mapreduce.Job: Running job: job_1500661353002_0001
17/07/21 19:28:07 INFO mapreduce.Job: Job job_1500661353002_0001 running in uber mode : false
17/07/21 19:28:07 INFO mapreduce.Job:  map 0% reduce 0%
17/07/21 19:28:26 INFO mapreduce.Job:  map 18% reduce 0%
17/07/21 19:28:27 INFO mapreduce.Job:  map 26% reduce 0%
17/07/21 19:28:29 INFO mapreduce.Job:  map 29% reduce 0%
17/07/21 19:28:30 INFO mapreduce.Job:  map 31% reduce 0%
17/07/21 19:28:31 INFO mapreduce.Job:  map 32% reduce 0%
17/07/21 19:28:32 INFO mapreduce.Job:  map 39% reduce 0%
17/07/21 19:28:33 INFO mapreduce.Job:  map 45% reduce 0%
17/07/21 19:28:34 INFO mapreduce.Job:  map 46% reduce 0%
17/07/21 19:28:35 INFO mapreduce.Job:  map 47% reduce 0%
17/07/21 19:28:37 INFO mapreduce.Job:  map 51% reduce 0%
17/07/21 19:28:39 INFO mapreduce.Job:  map 56% reduce 0%
17/07/21 19:28:40 INFO mapreduce.Job:  map 60% reduce 0%
17/07/21 19:28:41 INFO mapreduce.Job:  map 62% reduce 0%
17/07/21 19:28:42 INFO mapreduce.Job:  map 63% reduce 0%
17/07/21 19:28:44 INFO mapreduce.Job:  map 68% reduce 0%
17/07/21 19:28:45 INFO mapreduce.Job:  map 69% reduce 0%
17/07/21 19:28:46 INFO mapreduce.Job:  map 74% reduce 0%
17/07/21 19:28:47 INFO mapreduce.Job:  map 75% reduce 0%
17/07/21 19:28:48 INFO mapreduce.Job:  map 76% reduce 0%
17/07/21 19:28:50 INFO mapreduce.Job:  map 83% reduce 0%
17/07/21 19:28:51 INFO mapreduce.Job:  map 84% reduce 0%
17/07/21 19:28:52 INFO mapreduce.Job:  map 87% reduce 0%
17/07/21 19:28:53 INFO mapreduce.Job:  map 88% reduce 0%
17/07/21 19:28:54 INFO mapreduce.Job:  map 89% reduce 0%
17/07/21 19:28:56 INFO mapreduce.Job:  map 90% reduce 0%
17/07/21 19:28:57 INFO mapreduce.Job:  map 94% reduce 0%
17/07/21 19:28:58 INFO mapreduce.Job:  map 97% reduce 0%
17/07/21 19:28:59 INFO mapreduce.Job:  map 98% reduce 0%
17/07/21 19:29:00 INFO mapreduce.Job:  map 100% reduce 0%
17/07/21 19:29:11 INFO mapreduce.Job: Job job_1500661353002_0001 completed successfully
17/07/21 19:29:11 INFO mapreduce.Job: Counters: 33
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1533806
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1025
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=48
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=12
                Other local map tasks=12
                Total time spent by all maps in occupied slots (ms)=580423
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=580423
                Total vcore-milliseconds taken by all map tasks=580423
                Total megabyte-milliseconds taken by all map tasks=594353152
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=1025
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=71430
                CPU time spent (ms)=289230
                Physical memory (bytes) snapshot=1559642112
                Virtual memory (bytes) snapshot=8870043648
                Total committed heap usage (bytes)=289931264
                Peak Map Physical memory (bytes)=138743808
                Peak Map Virtual memory (bytes)=749912064
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
4.85user 0.26system 1:14.18elapsed 6%CPU (0avgtext+0avgdata 240904maxresident)k
0inputs+1048outputs (0major+34280minor)pagefaults 0swaps

//salida del comando hdfs dfs -ls /user/saturn/tgen

[root@ip-172-31-35-119 centos]# sudo -u hdfs hdfs dfs -ls /user/saturn/tgen
Found 13 items
-rw-r--r--   3 saturn saturn          0 2017-07-21 19:29 /user/saturn/tgen/_SUCCESS
-rw-r--r--   3 saturn saturn  546133400 2017-07-21 19:28 /user/saturn/tgen/part-m-00000
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00001
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00002
-rw-r--r--   3 saturn saturn  546133400 2017-07-21 19:28 /user/saturn/tgen/part-m-00003
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00004
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00005
-rw-r--r--   3 saturn saturn  546133400 2017-07-21 19:28 /user/saturn/tgen/part-m-00006
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00007
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00008
-rw-r--r--   3 saturn saturn  546133400 2017-07-21 19:28 /user/saturn/tgen/part-m-00009
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00010
-rw-r--r--   3 saturn saturn  546133300 2017-07-21 19:28 /user/saturn/tgen/part-m-00011



//

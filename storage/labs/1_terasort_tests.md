HDFS Lab: Test HDFS throughput

Create an end-user Linux account named with your GitHub handle
useradd nayibeorjuela -d /home/nayibeorjuela -p nayibeorjuela -s /bin/bash

Teragen
[centos@ip-172-31-40-153 hadoop-0.20-mapreduce]$ sudo -u nayibeorjuela time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapred.compress.map.output=false -Dmapreduce.jobs.maps=4 32000 /user/nayibeorjuela/teragen
17/07/19 20:39:27 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-40-153.us-west-2.compute.internal/172.31.40.153:8032
17/07/19 20:39:27 INFO terasort.TeraGen: Generating 32000 using 2
17/07/19 20:39:27 INFO mapreduce.JobSubmitter: number of splits:2
17/07/19 20:39:27 INFO Configuration.deprecation: mapred.compress.map.output is deprecated. Instead, use mapreduce.map.output.compress
17/07/19 20:39:28 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1500484772828_0003
17/07/19 20:39:28 INFO impl.YarnClientImpl: Submitted application application_1500484772828_0003
17/07/19 20:39:28 INFO mapreduce.Job: The url to track the job: http://ip-172-31-40-153.us-west-2.compute.internal:8088/proxy/application_1500484772828_0003/
17/07/19 20:39:28 INFO mapreduce.Job: Running job: job_1500484772828_0003
17/07/19 20:39:34 INFO mapreduce.Job: Job job_1500484772828_0003 running in uber mode : false
17/07/19 20:39:34 INFO mapreduce.Job: map 0% reduce 0%
17/07/19 20:39:40 INFO mapreduce.Job: map 100% reduce 0%
17/07/19 20:39:41 INFO mapreduce.Job: Job job_1500484772828_0003 completed successfully
17/07/19 20:39:41 INFO mapreduce.Job: Counters: 33
File System Counters
FILE: Number of bytes read=0
FILE: Number of bytes written=259444
FILE: Number of read operations=0
FILE: Number of large read operations=0
FILE: Number of write operations=0
HDFS: Number of bytes read=164
HDFS: Number of bytes written=3200000
HDFS: Number of read operations=8
HDFS: Number of large read operations=0
HDFS: Number of write operations=4
Job Counters
Launched map tasks=2
Other local map tasks=2
Total time spent by all maps in occupied slots (ms)=7470
Total time spent by all reduces in occupied slots (ms)=0
Total time spent by all map tasks (ms)=7470
Total vcore-milliseconds taken by all map tasks=7470
Total megabyte-milliseconds taken by all map tasks=7649280
Map-Reduce Framework
Map input records=32000
Map output records=32000
Input split bytes=164
Spilled Records=0
Failed Shuffles=0
Merged Map outputs=0
GC time elapsed (ms)=71
CPU time spent (ms)=3160
Physical memory (bytes) snapshot=398737408
Virtual memory (bytes) snapshot=3180965888
Total committed heap usage (bytes)=579862528
Peak Map Physical memory (bytes)=201383936
Peak Map Virtual memory (bytes)=1590956032
org.apache.hadoop.examples.terasort.TeraGen$Counters
CHECKSUM=68613941816777
File Input Format Counters
Bytes Read=0
File Output Format Counters
Bytes Written=3200000
6.11user 0.47system 0:17.22elapsed 38%CPU (0avgtext+0avgdata 187684maxresident)k
0inputs+968outputs (0major+35692minor)pagefaults 0swaps

Terasort
[centos@ip-172-31-40-153 hadoop-0.20-mapreduce]$ sudo -u nayibeorjuela time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/nayibeorjuela/teragen /user/nayibeorjuela/terasort
17/07/19 20:41:52 INFO terasort.TeraSort: starting
17/07/19 20:41:53 INFO input.FileInputFormat: Total input paths to process : 2
Spent 145ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 148ms
Sampling 2 splits of 2
Making 8 from 32000 sampled records
Computing parititions took 536ms
Spent 686ms computing partitions.
17/07/19 20:41:54 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-40-153.us-west-2.compute.internal/172.31.40.153:8032
17/07/19 20:41:55 INFO mapreduce.JobSubmitter: number of splits:2
17/07/19 20:41:55 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1500484772828_0004
17/07/19 20:41:55 INFO impl.YarnClientImpl: Submitted application application_1500484772828_0004
17/07/19 20:41:55 INFO mapreduce.Job: The url to track the job: http://ip-172-31-40-153.us-west-2.compute.internal:8088/proxy/application_1500484772828_0004/
17/07/19 20:41:55 INFO mapreduce.Job: Running job: job_1500484772828_0004
17/07/19 20:42:01 INFO mapreduce.Job: Job job_1500484772828_0004 running in uber mode : false
17/07/19 20:42:01 INFO mapreduce.Job: map 0% reduce 0%
17/07/19 20:42:09 INFO mapreduce.Job: map 100% reduce 0%
17/07/19 20:42:16 INFO mapreduce.Job: map 100% reduce 13%
17/07/19 20:42:20 INFO mapreduce.Job: map 100% reduce 25%
17/07/19 20:42:21 INFO mapreduce.Job: map 100% reduce 50%
17/07/19 20:42:22 INFO mapreduce.Job: map 100% reduce 75%
17/07/19 20:42:23 INFO mapreduce.Job: map 100% reduce 100%
17/07/19 20:42:24 INFO mapreduce.Job: Job job_1500484772828_0004 completed successfully
17/07/19 20:42:24 INFO mapreduce.Job: Counters: 54
File System Counters
FILE: Number of bytes read=1376753
FILE: Number of bytes written=4063118
FILE: Number of read operations=0
FILE: Number of large read operations=0
FILE: Number of write operations=0
HDFS: Number of bytes read=3200248
HDFS: Number of bytes written=3200000
HDFS: Number of read operations=30
HDFS: Number of large read operations=0
HDFS: Number of write operations=16
Job Counters
Launched map tasks=2
Launched reduce tasks=8
Data-local map tasks=1
Rack-local map tasks=1
Total time spent by all maps in occupied slots (ms)=11829
Total time spent by all reduces in occupied slots (ms)=65159
Total time spent by all map tasks (ms)=11829
Total time spent by all reduce tasks (ms)=65159
Total vcore-milliseconds taken by all map tasks=11829
Total vcore-milliseconds taken by all reduce tasks=65159
Total megabyte-milliseconds taken by all map tasks=12112896
Total megabyte-milliseconds taken by all reduce tasks=66722816
Map-Reduce Framework
Map input records=32000
Map output records=32000
Map output bytes=3264000
Map output materialized bytes=1376165
Input split bytes=248
Combine input records=0
Combine output records=0
Reduce input groups=32000
Reduce shuffle bytes=1376165
Reduce input records=32000
Reduce output records=32000
Spilled Records=64000
Shuffled Maps =16
Failed Shuffles=0
Merged Map outputs=16
GC time elapsed (ms)=841
CPU time spent (ms)=21510
Physical memory (bytes) snapshot=2870738944
Virtual memory (bytes) snapshot=15969488896
Total committed heap usage (bytes)=3437232128
Peak Map Physical memory (bytes)=513609728
Peak Map Virtual memory (bytes)=1597652992
Peak Reduce Physical memory (bytes)=254279680
Peak Reduce Virtual memory (bytes)=1609347072
Shuffle Errors
BAD_ID=0
CONNECTION=0
IO_ERROR=0
WRONG_LENGTH=0
WRONG_MAP=0
WRONG_REDUCE=0
File Input Format Counters
Bytes Read=3200000
File Output Format Counters
Bytes Written=3200000
17/07/19 20:42:24 INFO terasort.TeraSort: done
6.82user 0.47system 0:33.66elapsed 21%CPU (0avgtext+0avgdata 195540maxresident)k
0inputs+1008outputs (0major+32457minor)pagefaults 0swaps

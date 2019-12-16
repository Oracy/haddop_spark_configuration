# Avalia Filmes

```python
python AvaliaFilme.py hdfs:///mapred/u.data -r hadoop
```

**Expected result**

```bash
Using configs in /home/hadoop/.mrjob.conf
Looking for hadoop binary in /opt/hadoop/bin...
Found hadoop binary: /opt/hadoop/bin/hadoop
Using Hadoop version 3.2.1
Looking for Hadoop streaming jar in /opt/hadoop...
Found Hadoop streaming jar: /opt/hadoop/share/hadoop/tools/lib/hadoop-streaming-3.2.1.jar
Creating temp directory /tmp/AvaliaFilme.hadoop.20191216.171112.485214
uploading working dir files to hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214/files/wd...
Copying other local files to hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214/files/
Running step 1 of 1...
  packageJobJar: [/tmp/hadoop-unjar7739344483338428875/] [] /tmp/streamjob7398459970299040132.jar tmpDir=null
  Connecting to ResourceManager at /0.0.0.0:8032
  Connecting to ResourceManager at /0.0.0.0:8032
  Disabling Erasure Coding for path: /tmp/hadoop-yarn/staging/hadoop/.staging/job_1576507050328_0004
  SASL encryption trust check: localHostTrusted = false, remoteHostTrusted = false
  Total input files to process : 1
  SASL encryption trust check: localHostTrusted = false, remoteHostTrusted = false
  SASL encryption trust check: localHostTrusted = false, remoteHostTrusted = false
  number of splits:2
  SASL encryption trust check: localHostTrusted = false, remoteHostTrusted = false
  Submitting tokens for job: job_1576507050328_0004
  Executing with tokens: []
  resource-types.xml not found
  Unable to find 'resource-types.xml'.
  Submitted application application_1576507050328_0004
  The url to track the job: http://master-hadoop:8088/proxy/application_1576507050328_0004/
  Running job: job_1576507050328_0004
  Job job_1576507050328_0004 running in uber mode : false
   map 0% reduce 0%
   map 100% reduce 0%
   map 100% reduce 100%
  Job job_1576507050328_0004 completed successfully
  Output directory: hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214/output
Counters: 54
File Input Format Counters
    Bytes Read=1983269
File Output Format Counters
    Bytes Written=49
File System Counters
    FILE: Number of bytes read=800006
    FILE: Number of bytes written=2290581
    FILE: Number of large read operations=0
    FILE: Number of read operations=0
    FILE: Number of write operations=0
    HDFS: Number of bytes read=1983443
    HDFS: Number of bytes read erasure-coded=0
    HDFS: Number of bytes written=49
    HDFS: Number of large read operations=0
    HDFS: Number of read operations=11
    HDFS: Number of write operations=2
Job Counters
    Data-local map tasks=2
    Launched map tasks=2
    Launched reduce tasks=1
    Total megabyte-milliseconds taken by all map tasks=14288896
    Total megabyte-milliseconds taken by all reduce tasks=3928064
    Total time spent by all map tasks (ms)=13954
    Total time spent by all maps in occupied slots (ms)=13954
    Total time spent by all reduce tasks (ms)=3836
    Total time spent by all reduces in occupied slots (ms)=3836
    Total vcore-milliseconds taken by all map tasks=13954
    Total vcore-milliseconds taken by all reduce tasks=3836
Map-Reduce Framework
    CPU time spent (ms)=2300
    Combine input records=0
    Combine output records=0
    Failed Shuffles=0
    GC time elapsed (ms)=243
    Input split bytes=174
    Map input records=100000
    Map output bytes=600000
    Map output materialized bytes=800012
    Map output records=100000
    Merged Map outputs=2
    Peak Map Physical memory (bytes)=245039104
    Peak Map Virtual memory (bytes)=2544254976
    Peak Reduce Physical memory (bytes)=139722752
    Peak Reduce Virtual memory (bytes)=2548793344
    Physical memory (bytes) snapshot=629415936
    Reduce input groups=5
    Reduce input records=100000
    Reduce output records=5
    Reduce shuffle bytes=800012
    Shuffled Maps =2
    Spilled Records=200000
    Total committed heap usage (bytes)=587014144
    Virtual memory (bytes) snapshot=7637303296
Shuffle Errors
    BAD_ID=0
    CONNECTION=0
    IO_ERROR=0
    WRONG_LENGTH=0
    WRONG_MAP=0
    WRONG_REDUCE=0
job output is in hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214/output
Streaming final output from hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214/output...
STDERR: 2019-12-16 14:12:00,066 INFO sasl.SaslDataTransferClient: SASL encryption trust check: localHostTrusted = false, remoteHostTrusted = false
"1" 6110
"2" 11370
"3" 27145
"4" 34174
"5" 21201
Removing HDFS temp directory hdfs:///user/hadoop/tmp/mrjob/AvaliaFilme.hadoop.20191216.171112.485214...
Removing temp directory /tmp/AvaliaFilme.hadoop.20191216.171112.485214...
```

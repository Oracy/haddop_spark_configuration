# Install and Configure Pig

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/pig/pig-0.17.0/pig-0.17.0.tar.gz
tar -zxvf pig-0.17.0.tar.gz
sudo mkdir /usr/local/pig
sudo mv pig-0.17.0 /usr/local/pig
sudo ln -s /usr/local/pig/pig-0.17.0 /opt/pig
echo '# Pig' >> ~/.bashrc
echo 'export PIG_HOME=/opt/pig' >> ~/.bashrc
echo 'export PATH=$PATH:$PIG_HOME/bin' >> ~/.bashrc
echo 'export PIG_CLASSPATH=$HADOOP_HOME/conf' >> ~/.bashrc
source ~/.bashrc
pig
```

**Expected result**

```bash
2019-12-15 18:34:34,621 INFO pig.ExecTypeProvider: Trying ExecType : LOCAL
2019-12-15 18:34:34,622 INFO pig.ExecTypeProvider: Trying ExecType : MAPREDUCE
2019-12-15 18:34:34,622 INFO pig.ExecTypeProvider: Picked MAPREDUCE as the ExecType
2019-12-15 18:34:34,720 [main] INFO  org.apache.pig.Main - Apache Pig version 0.17.0 (r1797386) compiled Jun 02 2017, 15:41:58
2019-12-15 18:34:34,720 [main] INFO  org.apache.pig.Main - Logging error messages to: /home/hadoop/Downloads/pig_1576445674696.log
2019-12-15 18:34:34,741 [main] INFO  org.apache.pig.impl.util.Utils - Default bootup file /home/hadoop/.pigbootup not found
2019-12-15 18:34:35,205 [main] INFO  org.apache.hadoop.conf.Configuration.deprecation - mapred.job.tracker is deprecated. Instead, use mapreduce.jobtracker.address
2019-12-15 18:34:35,205 [main] INFO  org.apache.pig.backend.hadoop.executionengine.HExecutionEngine - Connecting to hadoop file system at: hdfs://localhost:9000
2019-12-15 18:34:35,954 [main] INFO  org.apache.pig.PigServer - Pig Script ID for the session: PIG-default-b40d79a3-c3c2-4e03-b981-3f3c95e4931f
2019-12-15 18:34:35,954 [main] WARN  org.apache.pig.PigServer - ATS is disabled since yarn.timeline-service.enabled set to false
grunt>
```

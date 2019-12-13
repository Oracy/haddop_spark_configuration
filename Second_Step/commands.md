# Commands

## DFS

```bash
# List all files on '/' in hdfs
hdfs dfs -ls /
# Create new folder called user in '/' on hdfs
hdfs dfs -mkdir /user
# Copy all files from hadoop to /user/hadoop
hdfs dfs -put /opt/hadoop/etc/hadoop/*.xml /user/hadoop

hdfs dfs -ls /user/hadoop/output
# To read result from mapreduce
hdfs dfs -cat /user/hadoop/output/part-r-00000
# Copy files from hdfs to local
hdfs dfs -get output output
```

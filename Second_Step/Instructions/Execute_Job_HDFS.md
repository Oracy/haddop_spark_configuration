# Execute Job in HDFS

```bash
cd /opt/hadoop/share/hadoop/mapreduce
ls
cd -
hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.1.jar grep /user/hadoop output 'dfs[a-z.]+'
# ALWAYS DO IT before shutdown (good practices)
stop-dfs.sh
```

**Expected result**

```bash
Stopping namenodes on [localhost]
Stopping datanodes
Stopping secondary namenodes [master-hadoop]
```

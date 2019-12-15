# Configure Yarn

Replace below files with files in `/opt/hadoop/etc/hadoop/`<br>
[mapred-site.xml](../mapred-site.xml)<br>
[yarn-site.xml](../yarn-site.xml)

```bash
start-dfs.sh
start-yarn.sh
jps
```

**Expected result**

```bash
# DFS
Starting namenodes on [localhost]
Starting datanodes
Starting secondary namenodes [master-hadoop]
# Yarn
Starting resourcemanager
Starting nodemanagers
# JPS
14450 NameNode
14786 SecondaryNameNode
15141 NodeManager
15030 ResourceManager
15478 Jps
14573 DataNode
```

You can access Yarn information on browser `http://<ip_address>:8088`

```bash
hdfs dfs -mkdir input
hdfs dfs -put /opt/hadoop/etc/hadoop/*.xml input
hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.1.jar grep input output_yarn 'dfs[a-z.]+'
```

# Configure HDFS and MapReduce

```bash
hdfs namenode -format
```

**Expected result**
`INFO common.Storage: Storage directory /tmp/hadoop-hadoop/dfs/name has been successfully formatted.`

Start Distributed Filesystem

```bash
start-dfs.sh
```

**Expected result**

```bash
Starting namenodes on [localhost]
Starting datanodes
Starting secondary namenodes [master-hadoop]
master-hadoop: Warning: Permanently added 'master-hadoop,fe80::677a:d821:c063:e1ad%enp0s3' (ECDSA) to the list of known hosts.
```

Check services related to Hadoop is running

```bash
jps
```

**Expected result**

```bash
23044 Jps
20871 NameNode
20987 DataNode
21227 SecondaryNameNode
```

You can access Namenode information on browser `http://<ip_address>:8970`

HDFS [Commands](./Second_Step/commands.md) and tests

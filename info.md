# Hadoop

Hadoop can be executed in three modes:

- Standalone
  - Configured to run as local mode, development moment.
- Pseudo-Distributed
  - Configured to run as local mode, but all configuration is as Cluster, but everything run as distributed.
- Fully Distributed
  - Distributed processing for production

---

Master

- NameNode;
  - HDFS Manager (distributed filesystem);
- JobTracker;
  - MapReduce job manager;
- SecondaryNameNode;
  - Work like a Backup although can do functions management.

Slaves (Workers)

- DataNode;
  - Storage and recovery data from HDFS;
- TaskTracer;
  - Execute Map Reduce.

---

[Hadoop Ecosystem Table](http://hadoopecosystemtable.github.io/)

---

```bash
start-dfs.sh
start-yarn.sh
zkServer.sh start
```

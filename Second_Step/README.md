# Second Step Hadoop

1. **Install Hadoop**

    Create new user for hadoop

    ```bash
    sudo adduser hadoop
    sudo passwd hadoop
    sudo vi /etc/sudoers
    # After line
    ## Allow root to run any commands anywhere
    # add this
    hadoop  ALL=(ALL)   ALL
    # will show something like
    ## Allow root to run any commands anywhere
    # root    ALL=(ALL)       ALL
    # hadoop  ALL=(ALL)       ALL
    # To change to hadoop user
    su - hadoop
    ```

    To install [hadoop](https://hadoop.apache.org/)

    ```bash
    wget http://ftp.unicamp.br/pub/apache/hadoop/common/hadoop-3.2.1/hadoop-3.2.1.tar.gz
    tar -zxvf hadoop-3.2.1.tar.gz
    sudo mkdir /usr/local/hadoop
    sudo mv hadoop-3.2.1 /usr/local/hadoop/
    sudo ln -s /usr/local/hadoop/hadoop-3.2.1/ /opt/hadoop
    echo '# JDK' >> ~/.bashrc
    echo 'export JAVA_HOME=/opt/java' >> ~/.bashrc
    echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.bashrc
    echo '# Hadoop' >> ~/.bashrc
    echo 'export HADOOP_HOME=/opt/hadoop'  >> ~/.bashrc
    echo 'export HADOOP_INSTALL=$HADOOP_HOME' >> ~/.bashrc
    echo 'export HADOOP_COMMON_HOME=$HADOOP_HOME' >> ~/.bashrc
    echo 'export HADOOP_MAPRED_HOME=$HADOOP_HOME' >> ~/.bashrc
    echo 'export HADOOP_HDFS_HOME=$HADOOP_HOME' >> ~/.bashrc
    echo 'export YARN_HOME=$HADOOP_HOME' >> ~/.bashrc
    echo 'export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin' >> ~/.bashrc
    ```

    **Configuring Hadoop in Pseudo-Distributed mode**
    Replace below files with files in `/opt/hadoop/etc/hadoop/`
    [core-site.xml](./Second_Step/core-site.xml)
    [hdfs-site.xml](./Second_Step/hdfs-site.xml)

    Create localhost trust connection

    ```bash
    ssh-keygen -t rsa
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
    chmod 600 ~/.ssh/authorized_keys
    ```

2. **Configure HDFS and MapReduce**

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

3. **Execute MapReduce Job on HDFS**

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

4. **Configure Yarn**

    Replace below files with files in `/opt/hadoop/etc/hadoop/`
    [mapred-site.xml](./Second_Step/mapred-site.xml)
    [yarn-site.xml](./Second_Step/yarn-site.xml)

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

5. **Install and configure Zookeeper**
6. **Install and configure Hbase**
7. **Install and configure Hive**
8. **Install and configure Pig**
9. **Install and configure Sqoop**
10. **Install and configure Spark**
11. **Install and configure Flume**

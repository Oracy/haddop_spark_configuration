# Second Step Hadoop

1. Install Hadoop

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
    Replace below files with files in this folder
    [core-site.xml](./Second_Step/core-site.xml)
    [hdfs-site.xml](./Second_Step/hdfs-site.xml)

    ```bash
    ssh-keygen -t rsa
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
    chmod 600 ~/.ssh/authorized_keys
    ```

2. Configure HDFS and MapReduce
3. Execute MapReduce Job on HDFS
4. Install and configure Zookeeper
5. Install and configure Hbase
6. Install and configure Hive
7. Install and configure Pig
8. Install and configure Sqoop
9. Install and configure Spark
10. Install and configure Flume

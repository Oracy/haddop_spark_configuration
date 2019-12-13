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

# Install and Configure Zookeeper

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/hbase/2.2.2/hbase-2.2.2-bin.tar.gz
tar -zxvf hbase-2.2.2-bin.tar.gz
sudo mkdir /usr/local/hbase
sudo mv hbase-2.2.2 /usr/local/hbase
sudo ln -s /usr/local/hbase/hbase-2.2.2 /opt/hbase
cd /opt/hbase/
mkdir hfiles
cd conf
```

Replace below files with files in `/opt/hbase/conf`
[hbase-env.sh](../hbase/hbase-env.sh)
[hbase-site.xml](../hbase/hbase-site.xml)

```bash
echo '# Hbase' >> ~/.bashrc
echo 'export HBASE_HOME=/opt/hbase' >> ~/.bashrc
echo 'export PATH=$PATH:$HBASE_HOME/bin' >> ~/.bashrc
source ~/.bashrc
start-hbase.sh
hbase shell
```

**Expected result**

```bash
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hadoop/hadoop-3.2.1/share/hadoop/common/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hbase/hbase-2.2.2/lib/client-facing-thirdparty/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.slf4j.impl.Log4jLoggerFactory]
running master, logging to /opt/hbase/logs/hbase-hadoop-master-master-hadoop.out
SLF4J: Class path contains multiple SLF4J bindings.
SLF4J: Found binding in [jar:file:/usr/local/hadoop/hadoop-3.2.1/share/hadoop/common/lib/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: Found binding in [jar:file:/usr/local/hbase/hbase-2.2.2/lib/client-facing-thirdparty/slf4j-log4j12-1.7.25.jar!/org/slf4j/impl/StaticLoggerBinder.class]
SLF4J: See http://www.slf4j.org/codes.html#multiple_bindings for an explanation.
SLF4J: Actual binding is of type [org.slf4j.impl.Log4jLoggerFactory]

hbase(main):001:0> help

```

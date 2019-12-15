# Install and Configure Zookeeper

```bash
cd Downloads
wget https://archive.apache.org/dist/zookeeper/zookeeper-3.5.5/apache-zookeeper-3.5.5-bin.tar.gz
tar -zxvf apache-zookeeper-3.5.5-bin.tar.gz
sudo mkdir /usr/local/zookeeper
sudo mv apache-zookeeper-3.5.5-bin /usr/local/zookeeper/
sudo ln -s /usr/local/zookeeper/apache-zookeeper-3.5.5-bin/ /opt/zookeeper
cd /opt/zookeeper/
mkdir data
cd conf
cp zoo_sample.cfg zoo.cfg
```

Replace below files with files in `/opt/zookeper/conf`
[zoo.cfg](../zookeeper/zoo.cfg)

```bash
echo '# Zookeeper' >> ~/.bashrc
echo 'export ZOOKEEPER_HOME=/opt/zookeeper' >> ~/.bashrc
echo 'export PATH=$PATH:$ZOOKEEPER_HOME/bin' >> ~/.bashrc
source ~/.bashrc
zkServer.sh start
```

**Expected result**

```bash
ZooKeeper JMX enabled by default
Using config: /opt/zookeeper/bin/../conf/zoo.cfg
Starting zookeeper ... STARTED
```

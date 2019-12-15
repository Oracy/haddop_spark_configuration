# Install and Configure Hive

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/hive/hive-3.1.2/apache-hive-3.1.2-bin.tar.gz
tar -zxvf apache-hive-3.1.2-bin.tar.gz
sudo mkdir /usr/local/hive
sudo mv apache-hive-3.1.2-bin /usr/local/hive
sudo ln -s /usr/local/hive/apache-hive-3.1.2-bin /opt/hive
cd /opt/hive/conf
```

Replace below files with files in `/opt/hive/conf`
[hive-env.sh](../hive/hive-env.sh)
[hive-default.xml](../hive/hive-default.xml)

```bash
hdfs dfs -mkdir /user/hive
hdfs dfs -mkdir /user/hive/warehouse
echo '# Hive' >> ~/.bashrc
echo 'export HIVE_HOME=/opt/hive' >> ~/.bashrc
echo 'export PATH=$PATH:$HIVE_HOME/bin' >> ~/.bashrc
source ~/.bashrc
cp /opt/hadoop/share/hadoop/common/lib/guava-27.0-jre.jar /opt/hive/lib
mv guava-19.0.jar guava-19.0.jar_bkp
schematool -dbType derby -initSchema
hive
# If there is some issue, run commands below
cd /usr/local/hive/apache-hive-3.1.2-bin
rm -rf metastore_db
cd /usr/local/hive/apache-hive-3.1.2-bin/lib
rm -rf metastore_db
```

**Expected result**

```bash
hive> show tables;
OK
Time taken: 0.653 seconds
hive>
```

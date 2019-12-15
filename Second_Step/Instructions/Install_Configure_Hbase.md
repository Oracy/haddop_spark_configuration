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
```

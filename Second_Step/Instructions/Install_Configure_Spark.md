# Install and Configure Spark

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/spark/spark-2.4.4/spark-2.4.4-bin-hadoop2.7.tgz
tar -zxvf spark-2.4.4-bin-hadoop2.7.tgz
sudo mkdir /usr/local/spark
sudo mv spark-2.4.4-bin-hadoop2.7 /usr/local/spark
sudo ln -s /usr/local/spark/spark-2.4.4-bin-hadoop2.7 /opt/spark
echo '# Spark' >> ~/.bashrc
echo 'SPARK_HOME=/opt/spark' >> ~/.bashrc
echo 'PATH=$PATH:$SPARK_HOME/bin' >> ~/.bashrc
source ~/.bashrc
```

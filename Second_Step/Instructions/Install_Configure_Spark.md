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
# For Scala
spark-shell
# For Python
pyspark
```

**Expected result Scala**

```bash
19/12/15 18:43:04 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
Spark context Web UI available at http://master-hadoop:4040
Spark context available as 'sc' (master = local[*], app id = local-1576446194844).
Spark session available as 'spark'.
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /___/ .__/\_,_/_/ /_/\_\   version 2.4.4
      /_/

Using Scala version 2.11.12 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_231)
Type in expressions to have them evaluated.
Type :help for more information.

scala>
```

**Expected result Python**

```bash
Python 2.7.5 (default, Aug  7 2019, 00:51:29) 
[GCC 4.8.5 20150623 (Red Hat 4.8.5-39)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
19/12/15 18:44:23 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /__ / .__/\_,_/_/ /_/\_\   version 2.4.4
      /_/

Using Python version 2.7.5 (default, Aug  7 2019 00:51:29)
SparkSession available as 'spark'.
>>>
```

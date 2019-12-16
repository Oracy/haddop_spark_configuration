# Install and Configure Sqoop

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist/sqoop/1.4.7/sqoop-1.4.7.bin__hadoop-2.6.0.tar.gz
tar -zxvf sqoop-1.4.7.bin__hadoop-2.6.0.tar.gz
sudo mkdir /usr/local/sqoop
sudo mv sqoop-1.4.7.bin__hadoop-2.6.0 /usr/local/sqoop
sudo ln -s /usr/local/sqoop/sqoop-1.4.7.bin__hadoop-2.6.0 /opt/sqoop
mkdir /opt/sqoop/accumulo
mkdir /opt/sqoop/hcatalog
```

Replace below files with files in `/opt/sqoop/conf`<br>
[sqoop-env.sh](../sqoop/sqoop-env.sh)

```bash
echo '# Sqoop' >> ~/.bashrc
echo 'export SQOOP_HOME=/opt/sqoop' >> ~/.bashrc
echo 'export PATH=$PATH:$SQOOP_HOME/bin' >> ~/.bashrc
echo 'export HCAT_HOME=/opt/sqoop/hcatalog' >> ~/.bashrc
echo 'export ACCUMULO_HOME=/opt/sqoop/accumulo' >> ~/.bashrc
source ~/.bashrc
sqoop version
```

**Expected result**

```bash
Error: Could not find or load main class org.apache.hadoop.hbase.util.GetJavaProperty
2019-12-15 18:56:54,078 INFO sqoop.Sqoop: Running Sqoop version: 1.4.7
Sqoop 1.4.7
git commit id 2328971411f57f0cb683dfb79d19d4d19d185dd8
Compiled by maugli on Thu Dec 21 15:59:58 STD 2017
```

---

## Configure MySQL in Sqoop

```bash
cd ~/Downloads
wget https://cdn.mysql.com//Downloads/Connector-J/mysql-connector-java-8.0.18.tar.gz
tar -zxvf mysql-connector-java-8.0.18.tar.gz
cd mysql-connector-java-8.0.18
cp mysql-connector-java-8.0.18.jar /opt/sqoop/lib/
```

### Sqoop USe

```bash
cd ~/Downloads
wget https://www-eu.apache.org/dist//commons/lang/binaries/commons-lang-2.6-bin.tar.gz
tar -zxvf commons-lang-2.6-bin.tar.gz
cd commons-lang-2.6-bin
cp commons-lang-2.6.jar /opt/sqoop/lib/
sqoop list-databases --connect jdbc:mysql://localhost:3306/ --username root -P
sqoop import --connect jdbc:mysql://localhost:3306/testedb --username root --password change_Password1 --table empregados -m 1
```

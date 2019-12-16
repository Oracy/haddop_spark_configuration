# Install and Configure MySQL

```bash
sudo yum localinstall https://dev.mysql.com/get/mysql80-community-release-el7-1.noarch.rpm
sudo yum install mysql-community-server
sudo systemctl enable mysqld
sudo systemctl start mysqld
sudo systemctl status mysqld
```

**Expected result**

```bash
● mysqld.service - MySQL Server
Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
Active: active (running) since Sex 2019-12-13 08:35:57 -03; 30s ago
    Docs: man:mysqld(8)
        http://dev.mysql.com/doc/refman/en/using-systemd.html
Process: 4022 ExecStartPre=/usr/bin/mysqld_pre_systemd (code=exited, status=0/SUCCESS)
Main PID: 4104 (mysqld)
Status: "Server is operational"
    Tasks: 39
CGroup: /system.slice/mysqld.service
        └─4104 /usr/sbin/mysqld

Dez 13 08:35:42 master-hadoop systemd[1]: Starting MySQL Server...
Dez 13 08:35:57 master-hadoop systemd[1]: Started MySQL Server.
```

## Configure Password

```bash
sudo systemctl stop mysqld
sudo mysqld --skip-grant-tables --user=mysql &
mysql
mysql> FLUSH PRIVILEGES;
SHOW VARIABLES LIKE 'validate_password%';
ALTER USER 'root'@'localhost' IDENTIFIED BY 'change_Password1';
quit
sudo shutdown -r now
mysql -u root -p
# To access remotely
mysql> CREATE USER 'hadoop'@'%' IDENTIFIED BY 'change_Password2';
mysql> GRANT ALL PRIVILEGES ON *.* TO 'hadoop'@'%';
mysql> FLUSH PRIVILEGES;
# If have some issues to login using DBeaver, follow the answer below
# https://community.atlassian.com/t5/Confluence-questions/MySQL-Public-Key-Retrieval-is-not-allowed/qaq-p/778956
```

### MySQL database

```sql
CREATE DATABASE testedb;
USE testedb;
CREATE TABLE empregados ( username VARCHAR(30), password VARCHAR(30) );
INSERT INTO empregados VALUE ( 'Alan Turing', 'password' );
```

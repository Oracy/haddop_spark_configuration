# First Step Hadoop

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Linux_Downloads)

2. Download [CentOS 7](http://isoredirect.centos.org/centos/7/isos/x86_64/)

3. Install utilities ([java](https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html), ssh, tools)

    After download CentOS, you can select this iso on VirtualBox and install that on our new machine. <br>
    Install Guest Additions on VirtualBox after CentOS installed.<br>

    You need to update kernel first.

    ```bash
    sudo yum update
    sudo yum -y install kernel-devel kernel-headers
    sudo yum -y install gcc make perl
    sudo yum -y install bzip2 unzip rsync wget net-tools
    sudo yum -y install openssh-server openssh-clients
    ```

    ```bash
    sudo systemctl enable sshd
    sudo systemctl start sshd
    sudo systemctl status sshd
    ```

    **Expected result**

    ```bash
    ● sshd.service - OpenSSH server daemon
    Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: enabled)
    Active: active (running) since Sex 2019-12-13 08:03:06 -03; 37min ago
        Docs: man:sshd(8)
            man:sshd_config(5)
    Main PID: 1376 (sshd)
        Tasks: 1
    CGroup: /system.slice/sshd.service
            └─1376 /usr/sbin/sshd -D

    Dez 13 08:03:06 master-hadoop systemd[1]: Starting OpenSSH server daemon...
    Dez 13 08:03:06 master-hadoop sshd[1376]: Server listening on 0.0.0.0 port 22.
    Dez 13 08:03:06 master-hadoop sshd[1376]: Server listening on :: port 22.
    Dez 13 08:03:06 master-hadoop systemd[1]: Started OpenSSH server daemon.
    Dez 13 08:05:23 master-hadoop sshd[3365]: Connection closed by 10.0.2.2 port...]
    Dez 13 08:05:34 master-hadoop sshd[3372]: Accepted password for root from 10...2
    Dez 13 08:08:22 master-hadoop sshd[3449]: Accepted password for root from 10...2
    Dez 13 08:36:14 master-hadoop sshd[4183]: Accepted password for root from 10...2
    Hint: Some lines were ellipsized, use -l to show in full.
    ```

    **Java**

    ```bash
    java -version
    ```

    **Expected result**

    ```bash
    openjdk version "1.8.0_232"
    OpenJDK Runtime Environment (build 1.8.0_232-b09)
    OpenJDK 64-Bit Server VM (build 25.232-b09, mixed mode)
    # We can see that OpenJDK is already installed on our server, but since Oracle have been
    # bought java, some applications runs better when Oracle JDK is installed instead of OpenJDK.
    # OpenJDK version is supported by community, instead of Oracle.
    ```

    ```bash
    sudo yum list java*
    sudo yum -y remove java*
    ```

    In my case I downloaded [jdk](https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html) from this link on my host machine and scp to VM

    ```bash
    tar -zxvf jdk-8u231-linux-x64.tar.gz
    sudo mkdir /usr/local/java
    sudo mv jdk1.8.0_231/ /usr/local/java/
    sudo ln -s /usr/local/java/jdk1.8.0_231 /opt/java
    echo '# Java Home' >> ~/.bashrc
    echo 'export JAVA_HOME=/opt/java' >> ~/.bashrc
    echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.bashrc
    source ~/.bashrc
    echo $JAVA_HOME
    java -version
    ```

    **Expected result**

    ```bash
    /opt/java
    java version "1.8.0_231"
    Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
    Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
    ```

    ```python
    Devices -> Insert Guest Additions CD Image... -> Run
    # Reboot VM
    ```

4. Install [MySQL](https://dev.mysql.com/doc/)

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

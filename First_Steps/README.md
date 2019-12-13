# First Steps Hadoop

1. Install [VirtualBox](https://www.virtualbox.org/wiki/Linux_Downloads)
2. Download [CentOS 7](http://isoredirect.centos.org/centos/7/isos/x86_64/)

After download CentOS, you can select this iso on VirtualBox and install that on our new machine. <br>
Install Guest Additions on VirtualBox after CentOS installed.<br>

You need to update kernel first.

```bash
sudo yum update
sudo yum install kernel-devel kernel-headers
sudo yum install gcc make perl
```

```
Devices -> Insert Guest Additions CD Image... -> Run
# Reboot VM
```
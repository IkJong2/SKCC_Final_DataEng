sudo hostnamectl set-hostname util.com
sudo hostnamectl set-hostname mn.com
sudo hostnamectl set-hostname dn1.com
sudo hostnamectl set-hostname dn2.com
sudo hostnamectl set-hostname dn3.com

# Final Exam
## 1. Create a CDH Cluster on AWS

### a. Linux setup
####  Add the following linux accounts to [all nodes]

1번: github 5번
2번: findmnt 
3번: df -Th
4번: github 6번
5번: ipconfig
6번: 재작년github hostname 설정
7번: github 7번
8번: github 8번


### c. Install Cloudera Manager
CDH version 5.15.2

```
sudo yum install wget
```

### Change VM Swappiness permanently
```
sudo vi /etc/sysctl.conf <=add vm.swappiness=1
```
![image](https://user-images.githubusercontent.com/52474199/124742257-7e5b6600-df57-11eb-89ca-7836bbdfc72b.png)

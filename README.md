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

### 3. Show the mount attributes of your volume(s)
```
$ cat /proc/mounts
$ cat /etc/fstab
```
![image](https://user-images.githubusercontent.com/52474199/124742812-0b062400-df58-11eb-8593-d1310d631f17.png)
![image](https://user-images.githubusercontent.com/52474199/124743022-43a5fd80-df58-11eb-9a19-21f7f1ffd910.png)

### 4. Disable Transparent Hugepage Support
```
sudo vi /etc/rc.d/rc.local
add ->
echo "never" > /sys/kernel/mm/transparent_hugepage/enabled
echo "never" > /sys/kernel/mm/transparent_hugepage/defrag
```
![image](https://user-images.githubusercontent.com/52474199/124743726-faa27900-df58-11eb-9d0e-fb311c1c7279.png)

```
sudo chmod +x /etc/rc.d/rc.local
```
```
sudo vi /etc/default/grub
 add -> transparent_hugepage=never (on line GRUB_CMDLINE_LINUX )
 ```
![image](https://user-images.githubusercontent.com/52474199/124744484-c5e2f180-df59-11eb-9f7a-537bc734e38e.png)

```
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```
![image](https://user-images.githubusercontent.com/52474199/124745041-56213680-df5a-11eb-9ec3-521fb023c4eb.png)

```
sudo systemctl start tuned
sudo tuned-adm off
sudo tuned-adm list
sudo systemctl stop tuned
sudo systemctl disable tuned
```
### 확인
```
$ cat /sys/kernel/mm/transparent_hugepage/enabled
```
```
$ cat /sys/kernel/mm/transparent_hugepage/defrag
```
![image](https://user-images.githubusercontent.com/52474199/124745838-31798e80-df5b-11eb-949c-356d1ee93b91.png)

# Linux File Systems

## dstat

* <https://www.linuxserver.io/2017/09/18/dstat-how-to-check-disk-io-in-linux/>

```
dnf install dstat

dstat -tdD total,sda,sdb,sdc,sdd 60
```

## Adding Hard Drives

* Refresh dev: <http://www.ehowstuff.com/how-to-add-a-new-hard-disk-without-rebooting-on-centos-7-rhel-7/>

	```
	[root@centos7 ~]# ls /sys/class/scsi_host/
	host0  host1  host2
	
	[root@centos7 ~]# echo "- - -" > /sys/class/scsi_host/host0/scan
	[root@centos7 ~]# echo "- - -" > /sys/class/scsi_host/host1/scan
	[root@centos7 ~]# echo "- - -" > /sys/class/scsi_host/host2/scan
	```

## Set Setuid, Setgid and Sticky bit in Linux

### Sticky bits

Assign  suid to a File :

```
# chmod  u+s testfile.txt OR #  chmod 4750  testfile.txt
```

In this example , 4 indicates SUID bitset, 7 for full permissions for owner, 5 for read and execute permissions for group, and no permissions for others.

SGID Example :

```
# chmod g+s OR # chmod 2750 
```

Here in 2750, 2 indicates SGID bitset, 7 for full permissions for owner, 5 for read and execute permissions for group, and no permissions for others.

StickyBit Example : 

```
# chmod o+t /opt/ftp-data  or # chmod +t /opt/ftp-data OR # chmod 1757 /opt/ftp-dta
```

In this example , 1 indicates Sticky Bit set, 7 for full permissions for owner, 5 for read and execute permissions for group, and ful permissions for others.

Note : To check the special permissions , use these commands :

```
# ls   -l  

# ls -ld   
```

### Resources

* <http://foralllinux.blogspot.com/2013/04/set-setuid-setgid-and-sticky-bit-in.html>
* <http://www.computernetworkingnotes.com/managing-file-system-security/sticky-bit.html>
* <https://docs.oracle.com/cd/E19683-01/816-4883/secfile-69/index.html>
* <https://linuxacademy.com/cp/courses/lesson/course/344/lesson/2/module/38>
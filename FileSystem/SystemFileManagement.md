### 1. View Logs:
```
cat /var/log/syslog (or /var/log/messages)
tail -f /var/log/syslog
journalctl -xe (for systemd logs)
```

### 2. Search Logs:
```
- grep "error" /var/log/syslog
- dmesg | grep "disk"
```

### 3. File Manipulation:
```
- cat /etc/passwd
- nano /etc/hosts
- vi /etc/fstab
```

### 4. Backup and Restore:
```
- rsync -av /source /destination
- tar -cvf backup.tar /directory
```

### 5. Package Management (related to system files):
```
- apt-get update && apt-get upgrade (Debian/Ubuntu)
- yum update (RHEL/CentOS)
- dnf update (Fedora)
```

### 6. System Configurations:
```
syntax: hostnamectl set-hostname new-hostname
ubuntu@ip-172-31-15-164:~$ hostnamectl set-hostname dev-server-01

ubuntu@ip-172-31-15-164:~$ hostnamectl
 Static hostname: dev-server-01
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: ec2afa4aa82a6da7e7ec6c1787c5a7be
         Boot ID: f5bc0a4113914806a8bac9673f853ae2
  Virtualization: xen
Operating System: Ubuntu 24.04 LTS
          Kernel: Linux 6.8.0-1009-aws
    Architecture: x86-64
 Hardware Vendor: Xen
  Hardware Model: HVM domU
Firmware Version: 4.11.amazon
   Firmware Date: Thu 2006-08-24
    Firmware Age: 17y 11month 3w 5d

```

```
syntax: timedatectl set-timezone region/city
ubuntu@ip-172-31-15-164:~$ timedatectl set-timezone America/New_York

ubuntu@ip-172-31-15-164:~$ timedatectl
               Local time: Mon 2024-08-19 06:55:39 EDT
           Universal time: Mon 2024-08-19 10:55:39 UTC
                 RTC time: Mon 2024-08-19 10:55:39
                Time zone: America/New_York (EDT, -0400)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no
```
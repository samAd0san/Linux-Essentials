### 1. df: Displays the amount of disk space available on the file system.
```
ubuntu@ip-172-31-15-164:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/root       6.8G  1.6G  5.2G  23% /
tmpfs           479M     0  479M   0% /dev/shm
tmpfs           192M  876K  191M   1% /run
tmpfs           5.0M     0  5.0M   0% /run/lock
/dev/xvda16     881M   76M  744M  10% /boot
/dev/xvda15     105M  6.1M   99M   6% /boot/efi
tmpfs            96M   12K   96M   1% /run/user/1000
```

### 2. du: Estimates file space usage.
```
ubuntu@ip-172-31-15-164:~$ pwd
/home/ubuntu

ubuntu@ip-172-31-15-164:~$ du -sh /home/ubuntu
56K     /home/ubuntu
ubuntu@ip-172-31-15-164:~$ lsblk
NAME     MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
loop0      7:0    0 25.2M  1 loop /snap/amazon-ssm-agent/7993
loop1      7:1    0 55.7M  1 loop /snap/core18/2829
loop2      7:2    0 38.8M  1 loop /snap/snapd/21759
xvda     202:0    0    8G  0 disk
├─xvda1  202:1    0    7G  0 part /
├─xvda14 202:14   0    4M  0 part
├─xvda15 202:15   0  106M  0 part /boot/efi
└─xvda16 259:0    0  913M  0 part /boot
```

### 3. lsblk: Lists information about all available block devices (like disks).
```
ubuntu@ip-172-31-15-164:~$ lsblk
NAME     MAJ:MIN RM  SIZE RO TYPE MOUNTPOINTS
loop0      7:0    0 25.2M  1 loop /snap/amazon-ssm-agent/7993
loop1      7:1    0 55.7M  1 loop /snap/core18/2829
loop2      7:2    0 38.8M  1 loop /snap/snapd/21759
xvda     202:0    0    8G  0 disk
├─xvda1  202:1    0    7G  0 part /
├─xvda14 202:14   0    4M  0 part
├─xvda15 202:15   0  106M  0 part /boot/efi
└─xvda16 259:0    0  913M  0 part /boot
```

### 4. iostat: Reports CPU and I/O statistics.
```
ubuntu@ip-172-31-15-164:~$ iostat
Linux 6.8.0-1009-aws (ip-172-31-15-164)         08/19/24        _x86_64_        (1 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           3.69    0.00    1.26    0.74    2.59   91.71

Device             tps    kB_read/s    kB_wrtn/s    kB_dscd/s    kB_read    kB_wrtn    kB_dscd
loop0             0.41        11.41         0.00         0.00       4029          0          0
loop1             0.14         1.02         0.00         0.00        360          0          0
loop2             0.15         1.05         0.00         0.00        370          0          0
loop3             0.03         0.04         0.00         0.00         14          0          0
xvda             25.37       704.94       541.90         0.00     248893     191330          0

ubuntu@ip-172-31-15-164:~$ iostat -dx
Linux 6.8.0-1009-aws (ip-172-31-15-164)         08/19/24        _x86_64_        (1 CPU)

Device            r/s     rkB/s   rrqm/s  %rrqm r_await rareq-sz     w/s     wkB/s   wrqm/s  %wrqm w_await wareq-sz     d/s     dkB/s   drqm/s  %drqm d_await dareq-sz     f/s f_await  aqu-sz  %util
loop0            0.23      6.39     0.00   0.00    0.70    27.79    0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00    0.00    0.00   0.03
loop1            0.08      0.57     0.00   0.00    0.46     7.50    0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00    0.00    0.00   0.01
loop2            0.08      0.59     0.00   0.00    0.34     6.98    0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00    0.00    0.00   0.01
loop3            0.02      0.02     0.00   0.00    0.09     1.27    0.00      0.00     0.00   0.00    0.00     0.00    0.00      0.00     0.00   0.00    0.00     0.00    0.00    0.00    0.00   0.00
xvda            10.23    398.04     3.69  26.53    1.32    38.92    4.26    304.24     5.12  54.60    2.78    71.47    0.00      0.00     0.00   0.00    0.00     0.00    0.00    0.00    0.03   1.45
```
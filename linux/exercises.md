# Exercises - List of exercises to do daily to improve linux skills

```
# Current time
# How long the system has been running
# How many users are currently logged on
# System load averages for the past 1, 5, and 15 minutes
# This is the same information contained in the header line displayed by 'w'
$ uptime

# See every process on the system
$ ps aux

# To print a process tree
$ ps auxf

# Investigate sockets
# -t --tcp       Display TCP sockets
# -u --udp       Display UDP sockets
# -p --processes Show process using socket
# -l --listening Display only listening sockets
# -n --numeric   Do not try to resolve services names
$ ss -tupln

# Report virtual memory statistics
# r: The number of runnable processes
# b: The number of processes blocked waiting for I/O to complete
$ vmstat

# Summary memory statistics
$ vmstat -s

# Display amount of free and used memory in the system
# 'total'      Total usable memory (MemTotal and SwapTotal in /proc/meminfo)
# 'used'       Used or unavailable memroy (calculated as 'total' - 'available')
# 'free'       Unused memroy (MemFree and SwapFree in /proc/meminfo)
# 'shared'     Memory used (mostly) by tmpfs (Shmem in /proc/meminfo)
# 'buffers'    Memory used by kernel buffers (Buffers in /proc/meminfo)
# 'cache'      Memory used by the page cache and slabs (Cached and SReclaimable in /proc/meminfo)
# 'buff/cache' Sum of buffers and cache
# 'available'  Estimation of how much memory is available for starting new applications, without swapping.
$ free -h

journalctl -k | grep -i oom

# This  file  reports  statistics  about memory usage on the system
$ cat /proc/meminfo

# Arguments  passed  to the linux kernel at boot time
$ cat /proc/cmdline

# CPU
top

# package sysstat
mpstat -P ALL # cpu balance

lscpu

pidstat
pidstat 1
pidstat -p $pid

# disk
vmstat -d
df -h
df -i
iostat -xz 1

# biggest files in /
du -mxS / | sort -n | tail -10

# network
sar -n DEV 1 # network throughput
sar -n TCP,ETCP 1 # TCP stats (also: ss -s)

# distro
cat /etc/???
lsb_release -a # lsb-release package

# boot
dmesg | tail
last -a
```

### Logging

```
journalctl
journalctl -f
journalctl -n 20 --no-pager -u nginx # last lines for a specific unit
journalctl --since yesterday --until "1 hour ago"
journalctl -k # kernel messages, dmesg
journalctl -p err # 0, 1, 2, 3 ...
```

### systemd

```
systemctl # same as systemctl list-units
systemctl cat <service> # shows location and contents of config file for <service>
systemctl list-unit-files # lists if they are masked (won't start, use unmask option)
systemctl reload unit # reload options after changes, install

systemctl --failed
systemd-analyze # startup time, append 'blame' for breakdown
```

### Filesystems and volumes

```
fdisk -l
df -lT # -l local, -T type
lsblk -f # filesystem
file -s /dev/***
blkid /dev/***

mount
cat /etc/fstab

fsck ???
```

### Networking

```
ss -s
ip -s
ip -s link
ip address
ip link
lsof -i
sar -n DEV

ip route

iptables -L
iptables -t nat -L # does not show with -L
```

curl options:

```
curl -v
curl -I # header info
curl -L # follow location
curl -O # download original name
```

### Kernel

```
uname -a
sysctl -a
```

### strace

```
strace -p $pid        # running program
strace -c $program    # run & summary
strace -e trace=write # filter

# Also info under /proc/$pid/
```

### SSL/TLS

```
openssl x509 -in /path/to/server/certificate -text
openssl s_client -connect example.com:443
	HEAD / HTTP/1.1
	Host: example.com

openssl s_client -connect example.com:443 -servername example.com -showcerts | openssl x509 -text -noout
```

### cgroups

```
# Ulimits for current bash session set at /etc/security/limits.conf
su - username -c 'ulimit -a'
cat /proc/cgroups
```

### Docker

```
docker ps -a
docker stats --all

docker logs <container>
docker inspect  <container>
docker diff <container>     # files changed
docker top <container>

docker update --help # update memory/cpu settings running container:
docker update -m 10M -c 2 <container>

# override entrypoint or command:
docker run -it --entrypoint /bin/bash <image>
docker run -it <image> /bin/bash
```

### Kubernetes

```
```

### DNS

```
host example.com
dig +short example.com
dig @ns_ip example.com
nslookup example.com # resolves and tells you what DNS server you are using

critical files:
/etc/nsswitch.conf # order of resolving
/etc/resolv.conf   # nameservers
/etc/hosts         # hard-coded hostname-ip maps
```

# nginx

```
nginx -t # test configuration
nginx -T # test and dump configuration
``

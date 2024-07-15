---
title: linu_troubleshooting_commands
description: linu_troubleshooting_commands
layout: libdoc/page

#LibDoc specific below
category: Troubleshooting
order: 90
#unlisted: true
---
* 
{:toc}


# Linux Commands Cheat Sheet

## Basic Commands

### File and Directory Management

#### 1. `ls`
```bash
ls
ls -l
ls -a
```

#### 2. `cd`
```bash
cd /path/to/directory
cd ..
```

#### 3. `mkdir`
```bash
mkdir new_directory
mkdir -p parent/child/grandchild
```

#### 4. `cp`
```bash
cp file1 file2
cp -r dir1 dir2
```

#### 5. `mv`
```bash
mv file1 file2
mv dir1 /path/to/new/location
```

### Text Processing

#### 6. `cat`
```bash
cat filename
cat file1 file2 > merged_file
```

#### 7. `grep`
```bash
grep pattern file
grep -r pattern directory
```

### System Information

#### 8. `uname`
```bash
uname -a
```

#### 9. `uptime`
```bash
uptime
```

### User Management

#### 10. `whoami`
```bash
whoami
```

#### 11. `sudo`
```bash
sudo command
```

### Network Management

#### 12. `ifconfig`
```bash
ifconfig
ifconfig eth0 up
```

#### 13. `ping`
```bash
ping example.com
```

### Package Management (APT)

#### 14. `apt-get`
```bash
sudo apt-get update
sudo apt-get install package_name
```

#### 15. `dpkg`
```bash
dpkg -i package.deb
```

### Process Management

#### 16. `ps`
```bash
ps
ps aux | grep process_name
```

#### 17. `kill`
```bash
kill PID
killall process_name
```

### File Permissions

#### 18. `chmod`
```bash
chmod u+x file
chmod 755 file
```

#### 19. `chown`
```bash
chown user:group file
```

### Advanced Commands

#### 20. `find`
```bash
find /path/to/search -name "pattern"
```

#### 21. `tar`
```bash
tar -cvzf archive.tar.gz /path/to/directory
tar -xvzf archive.tar.gz
```

#### 22. `awk`
```bash
awk '{print $1}' filename
```

#### 23. `sed`
```bash
sed 's/search/replace/g' filename
```

### Troubleshooting Commands

#### 24. `dmesg`
```bash
dmesg
dmesg | tail
```

#### 25. `journalctl`
```bash
journalctl
journalctl -u service_name
```

#### 26. `netstat`
```bash
netstat -tuln
netstat -an | grep LISTEN
```

#### 27. `top`
```bash
top
```

#### 28. `lsof`
```bash
lsof -i :port_number
lsof -i -n -P
```

### Conclusion

This cheat sheet covers basic to advanced Linux commands commonly used in system administration, troubleshooting, and everyday tasks. Adjust commands as per your specific Linux distribution and environment.
```

This structure now includes a section dedicated to troubleshooting commands commonly used for diagnosing issues on Linux systems. Adjust the commands and examples according to your specific needs and environment.

<!-- linux ethical hacking commands-->

Certainly! Here's an expanded section with more commands commonly used in ethical hacking and penetration testing scenarios:

```markdown
# Linux Commands Cheat Sheet

## Basic Commands

### File and Directory Management

#### 1. `ls`
```bash
ls
ls -l
ls -a
```

#### 2. `cd`
```bash
cd /path/to/directory
cd ..
```

#### 3. `mkdir`
```bash
mkdir new_directory
mkdir -p parent/child/grandchild
```

#### 4. `cp`
```bash
cp file1 file2
cp -r dir1 dir2
```

#### 5. `mv`
```bash
mv file1 file2
mv dir1 /path/to/new/location
```

### Text Processing

#### 6. `cat`
```bash
cat filename
cat file1 file2 > merged_file
```

#### 7. `grep`
```bash
grep pattern file
grep -r pattern directory
```

### System Information

#### 8. `uname`
```bash
uname -a
```

#### 9. `uptime`
```bash
uptime
```

### User Management

#### 10. `whoami`
```bash
whoami
```

#### 11. `sudo`
```bash
sudo command
```

### Network Management

#### 12. `ifconfig`
```bash
ifconfig
ifconfig eth0 up
```

#### 13. `ping`
```bash
ping example.com
```

### Package Management (APT)

#### 14. `apt-get`
```bash
sudo apt-get update
sudo apt-get install package_name
```

#### 15. `dpkg`
```bash
dpkg -i package.deb
```

### Process Management

#### 16. `ps`
```bash
ps
ps aux | grep process_name
```

#### 17. `kill`
```bash
kill PID
killall process_name
```

### File Permissions

#### 18. `chmod`
```bash
chmod u+x file
chmod 755 file
```

#### 19. `chown`
```bash
chown user:group file
```

### Advanced Commands

#### 20. `find`
```bash
find /path/to/search -name "pattern"
```

#### 21. `tar`
```bash
tar -cvzf archive.tar.gz /path/to/directory
tar -xvzf archive.tar.gz
```

#### 22. `awk`
```bash
awk '{print $1}' filename
```

#### 23. `sed`
```bash
sed 's/search/replace/g' filename
```

### Ethical Hacking Commands

#### 24. `nmap`
```bash
nmap -sS -A -O target_ip
nmap -p 1-65535 -sV -sS -T4 target_ip
```

#### 25. `netcat`
```bash
nc -nvlp port_number
```

#### 26. `hydra`
```bash
hydra -l username -P /path/to/wordlist.txt ssh://target_ip
hydra -L /path/to/usernames.txt -P /path/to/passwords.txt ftp://target_ip
```

#### 27. `metasploit`
```bash
msfconsole
```

#### 28. `sqlmap`
```bash
sqlmap -u "http://target_url/vulnerable.php?id=1"
```

#### 29. `aircrack-ng`
```bash
aircrack-ng -w /path/to/wordlist.txt capturefile.cap
```

#### 30. `john`
```bash
john --wordlist=/path/to/wordlist.txt --format=NT hash.txt
```

#### 31. `wireshark`
```bash
wireshark
```

#### 32. `tcpdump`
```bash
tcpdump -i eth0 -n host target_ip and port port_number
```

### Conclusion

This cheat sheet covers basic to advanced Linux commands commonly used in system administration, troubleshooting, and ethical hacking scenarios. Adjust commands as per your specific Linux distribution and environment.
```

This section now includes a broader range of commands used in ethical hacking, including tools for network scanning, password cracking, exploiting vulnerabilities, and analyzing network traffic. Adjust the commands and examples according to your specific needs and ethical considerations.

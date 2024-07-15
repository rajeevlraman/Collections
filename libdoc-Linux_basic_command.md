---
title: Linux_basic_command
description: Linux_basic_command
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 206
#unlisted: true
---
* 
{:toc}


#### 5. `cp`
```bash
cp file1 file2
cp -r dir1 dir2
```

#### 6. `mv`
```bash
mv file1 file2
mv dir1 /path/to/new/location
```

### Text Processing

#### 7. `cat`
```bash
cat filename
cat file1 file2 > merged_file
```

#### 8. `grep`
```bash
grep pattern file
grep -r pattern directory
```

### System Information

#### 9. `uname`
```bash
uname -a
```

#### 10. `uptime`
```bash
uptime
```

### User Management

#### 11. `whoami`
```bash
whoami
```

#### 12. `sudo`
```bash
sudo command
```

### Network Management

#### 13. `ifconfig`
```bash
ifconfig
ifconfig eth0 up
```

#### 14. `ping`
```bash
ping example.com
```

### Package Management (APT)

#### 15. `apt-get`
```bash
sudo apt-get update
sudo apt-get install package_name
```

#### 16. `dpkg`
```bash
dpkg -i package.deb
```

### Process Management

#### 17. `ps`
```bash
ps
ps aux | grep process_name
```

#### 18. `kill`
```bash
kill PID
killall process_name
```

### File Permissions

#### 19. `chmod`
```bash
chmod u+x file
chmod 755 file
```

#### 20. `chown`
```bash
chown user:group file
```

### Advanced Commands

#### 21. `find`
```bash
find /path/to/search -name "pattern"
```

#### 22. `tar`
```bash
tar -cvzf archive.tar.gz /path/to/directory
tar -xvzf archive.tar.gz
```

#### 23. `awk`
```bash
awk '{print $1}' filename
```

#### 24. `sed`
```bash
sed 's/search/replace/g' filename
```

### Conclusion

This cheat sheet covers basic to advanced Linux commands commonly used in system administration and everyday tasks. Adjust commands as per your specific Linux distribution and environment.
```

This Markdown code block contains titles and corresponding commands categorized into sections. Adjust the commands and examples as per your specific needs and Linux distribution.

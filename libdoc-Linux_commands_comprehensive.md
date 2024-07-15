---
title: Linux_commands_comprehensive
description: Linux_commands_comprehensive
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 208
#unlisted: true
---
* 
{:toc}


Sure, here's a comprehensive markdown page with Linux commands categorized by their functionalities:

# Comprehensive Linux Command Reference

## Categories:
- [File and Directory Management](#file-and-directory-management)
- [File Viewing and Editing](#file-viewing-and-editing)
- [File Permissions](#file-permissions)
- [Process Management](#process-management)
- [System Information](#system-information)
- [Networking](#networking)
- [User and Group Management](#user-and-group-management)
- [System Maintenance Tasks](#system-maintenance-tasks)
- [Package Management (distribution-dependent)](#package-management-distribution-dependent)
- [Compression and Archive Utilities](#compression-and-archive-utilities)
- [Security and Access Control](#security-and-access-control)
- [Virtualization and Container Management](#virtualization-and-container-management)
- [Miscellaneous Commands](#miscellaneous-commands)
- [Text Processing Utilities](#text-processing-utilities)
- [Development and Debugging](#development-and-debugging)
- [SSH and Remote Management](#ssh-and-remote-management)
- [Useful Shortcuts and Tips](#useful-shortcuts-and-tips)

---

## File and Directory Management
[Back to top](#categories)

- **`ls`**: List directory contents.
  ```bash
  ls
  ls -la



```markdown
# Linux Commands

## File and Directory Management:
- **`ls`**: List directory contents.
  ```bash
  ls -l        # Long listing
  ls -a        # Include hidden files
  ls -lh       # Human-readable sizes
  ```

- **`cd`**: Change directory.
  ```bash
  cd /path/to/directory
  cd ~         # Home directory
  cd ..        # Parent directory
  ```

- **`pwd`**: Print working directory.
  ```bash
  pwd
  ```

- **`mkdir`**: Make directories.
  ```bash
  mkdir newdir
  mkdir -p /path/to/parentdir/newdir  # Create parent directories as needed
  ```

- **`rmdir`**: Remove empty directories.
  ```bash
  rmdir dir
  ```

- **`rm`**: Remove files or directories.
  ```bash
  rm file.txt
  rm -r dir    # Recursive removal
  rm -f file   # Force removal
  ```

- **`cp`**: Copy files or directories.
  ```bash
  cp file1 file2
  cp -r dir1 dir2  # Copy directory recursively
  ```

- **`mv`**: Move or rename files or directories.
  ```bash
  mv oldname newname
  mv /path/to/source /path/to/destination
  ```

- **`touch`**: Create an empty file or update the timestamp.
  ```bash
  touch newfile.txt
  ```

- **`find`**: Search for files and directories.
  ```bash
  find /path -name "filename"
  find /path -type f -mtime -1  # Files modified in the last day
  ```

- **`locate`**: Quickly find files by name.
  ```bash
  locate filename
  ```

- **`updatedb`**: Update the database for the `locate` command.
  ```bash
  updatedb
  ```

- **`ln`**: Create hard and symbolic links.
  ```bash
  ln file link      # Hard link
  ln -s file link   # Symbolic link
  ```

- **`tree`**: Display directory tree.
  ```bash
  tree /path/to/directory
  ```
[Back to top](#categories)
## File Viewing and Editing:
- **`cat`**: Concatenate and display file content.
  ```bash
  cat file.txt
  ```

- **`tac`**: Display file content in reverse.
  ```bash
  tac file.txt
  ```

- **`more`**: View file content page by page.
  ```bash
  more file.txt
  ```

- **`less`**: View file content with backward movement.
  ```bash
  less file.txt
  ```

- **`head`**: Display the first lines of a file.
  ```bash
  head -n 10 file.txt  # First 10 lines
  ```

- **`tail`**: Display the last lines of a file.
  ```bash
  tail -n 10 file.txt  # Last 10 lines
  tail -f file.txt     # Follow the file updates
  ```

- **`nano`**: Command-line text editor.
  ```bash
  nano file.txt
  ```

- **`vi`** or **`vim`**: Advanced text editor.
  ```bash
  vi file.txt
  vim file.txt
  ```

- **`grep`**: Search text using patterns.
  ```bash
  grep "pattern" file.txt
  grep -r "pattern" /path  # Recursive search
  ```

- **`diff`**: Compare the differences between files.
  ```bash
  diff file1.txt file2.txt
  ```

- **`sed`**: Stream editor for filtering and transforming text.
  ```bash
  sed 's/old/new/' file.txt  # Replace 'old' with 'new'
  sed -i 's/old/new/g' file.txt  # In-place replacement
  ```

- **`awk`**: Pattern scanning and processing language.
  ```bash
  awk '{print $1}' file.txt  # Print first field of each line
  awk '/pattern/ {print $0}' file.txt  # Print lines matching pattern
  ```
[Back to top](#categories)
## File Permissions:
- **`chmod`**: Change file modes or Access Control Lists.
  ```bash
  chmod 755 file.txt    # Set permissions
  chmod u+x file.txt    # Add execute permission to the user
  ```

- **`chown`**: Change file owner and group.
  ```bash
  chown user:group file.txt
  chown -R user:group /path/to/directory  # Recursive change
  ```

- **`chgrp`**: Change group ownership.
  ```bash
  chgrp group file.txt
  ```

- **`umask`**: Set the default file creation permissions.
  ```bash
  umask 022
  ```

- **`lsattr`**: List file attributes on a Linux file system.
  ```bash
  lsattr file.txt
  ```

- **`chattr`**: Change file attributes on a Linux file system.
  ```bash
  chattr +i file.txt  # Make file immutable
  ```
[Back to top](#categories)
## Process Management:
- **`ps`**: Report a snapshot of current processes.
  ```bash
  ps aux           # Detailed process information
  ps -ef           # Full-format listing
  ```

- **`top`**: Display and update sorted process information.
  ```bash
  top
  ```

- **`htop`**: Interactive process viewer (requires installation).
  ```bash
  htop
  ```

- **`kill`**: Terminate a process by PID.
  ```bash
  kill PID
  kill -9 PID      # Force kill
  ```

- **`pkill`**: Kill processes by name.
  ```bash
  pkill process_name
  pkill -u username  # Kill all processes of a user
  ```

- **`killall`**: Kill all processes by name.
  ```bash
  killall process_name
  ```

- **`bg`**: Resume a suspended job in the background.
  ```bash
  bg %job_id
  ```

- **`fg`**: Bring a background job to the foreground.
  ```bash
  fg %job_id
  ```

- **`jobs`**: List background jobs.
  ```bash
  jobs
  ```

- **`nice`**: Start a process with a given priority.
  ```bash
  nice -n 10 command
  ```

- **`renice`**: Change the priority of a running process.
  ```bash
  renice +10 PID
  ```

- **`nohup`**: Run a command immune to hangups.
  ```bash
  nohup command &
  ```

- **`systemctl`**: Control the systemd system and service manager.
  ```bash
  systemctl status service
  systemctl start service
  systemctl stop service
  systemctl restart service
  ```

- **`service`**: Run a System V init script.
  ```bash
  service service_name start
  service service_name stop
  service service_name restart
  ```
[Back to top](#categories)
## System Information:
- **`uname`**: Print system information.
  ```bash
  uname -a      # All system information
  uname -r      # Kernel version
  ```

- **`hostname`**: Show or set the system's host name.
  ```bash
  hostname
  ```

- **`uptime`**: Tell how long the system has been running.
  ```bash
  uptime
  ```

- **`dmesg`**: Print kernel ring buffer messages.
  ```bash
  dmesg
  ```

- **`df`**: Report file system disk space usage.
  ```bash
  df -h         # Human-readable format
  ```

- **`du`**: Estimate file space usage.
  ```bash
  du -sh *      # Human-readable total for each item
  du -ch        # Human-readable cumulative sizes
  ```

- **`free`**: Display amount of free and used memory in the system.
  ```bash
  free -h       # Human-readable format
  ```

- **`vmstat`**: Report virtual memory statistics.
  ```bash
  vmstat
  ```

- **`iostat`**: Report CPU and I/O statistics.
  ```bash
  iostat
  ```

- **`lsof`**: List open files.
  ```bash
  lsof
  lsof -i       # List network files
  ```

- **`netstat`**: Print network connections, routing tables, interface statistics.
  ```bash
  netstat -tuln   # Listening ports
  netstat -anp    # All connections with process ID
  ```

- **`ifconfig`**: Configure a network interface.
  ```bash
  ifconfig
  ```

- **`ip`**: Show/manipulate routing, devices, policy routing

, and tunnels.
  ```bash
  ip a         # Display all IP addresses
  ip link      # Display link layer information
  ```

- **`route`**: Show/manipulate the IP routing table.
  ```bash
  route -n
  ```

- **`ss`**: Utility to investigate sockets.
  ```bash
  ss -tuln     # List open ports
  ```

- **`who`**: Show who is logged on.
  ```bash
  who
  ```

- **`w`**: Show who is logged on and what they are doing.
  ```bash
  w
  ```

- **`last`**: Show listing of last logged in users.
  ```bash
  last
  ```

- **`uptime`**: Show how long the system has been running.
  ```bash
  uptime
  ```
[Back to top](#categories)
## Networking:
- **`ping`**: Send ICMP ECHO_REQUEST to network hosts.
  ```bash
  ping hostname_or_ip
  ```

- **`traceroute`**: Print the route packets take to the network host.
  ```bash
  traceroute hostname_or_ip
  ```

- **`curl`**: Transfer a URL.
  ```bash
  curl http://example.com
  curl -O http://example.com/file  # Download a file
  ```

- **`wget`**: Retrieve files from the web.
  ```bash
  wget http://example.com/file
  wget -c http://example.com/file  # Continue a partially downloaded file
  ```

- **`scp`**: Securely copy files between hosts.
  ```bash
  scp localfile user@remote:/path/to/remote/file
  scp user@remote:/path/to/remote/file localfile
  ```

- **`rsync`**: Sync files and directories to/from a remote system.
  ```bash
  rsync -avz source destination
  rsync -avz /path/to/source user@remote:/path/to/destination
  ```

- **`ftp`**: File Transfer Protocol client.
  ```bash
  ftp hostname_or_ip
  ```

- **`sftp`**: Secure File Transfer Protocol client.
  ```bash
  sftp user@hostname_or_ip
  ```

- **`telnet`**: User interface to the TELNET protocol.
  ```bash
  telnet hostname_or_ip
  ```

- **`ssh`**: OpenSSH SSH client (remote login program).
  ```bash
  ssh user@hostname_or_ip
  ```

- **`nmap`**: Network exploration tool and security/port scanner.
  ```bash
  nmap hostname_or_ip
  ```

- **`ip`**: Show/manipulate routing, devices, policy routing, and tunnels.
  ```bash
  ip addr show            # Show all IP addresses
  ip link set eth0 up     # Bring interface up
  ip link set eth0 down   # Bring interface down
  ```
[Back to top](#categories)
## User and Group Management:
- **`useradd`**: Create a new user or update default new user information.
  ```bash
  useradd username
  useradd -m username  # Create home directory
  ```

- **`usermod`**: Modify a user account.
  ```bash
  usermod -aG groupname username  # Add user to a group
  usermod -L username  # Lock user account
  usermod -U username  # Unlock user account
  ```

- **`userdel`**: Delete a user account and related files.
  ```bash
  userdel username
  userdel -r username  # Remove home directory
  ```

- **`passwd`**: Change user password.
  ```bash
  passwd username
  ```

- **`groupadd`**: Create a new group.
  ```bash
  groupadd groupname
  ```

- **`groupdel`**: Delete a group.
  ```bash
  groupdel groupname
  ```

- **`groups`**: Show which groups a user is a member of.
  ```bash
  groups username
  ```

- **`id`**: Display user identity.
  ```bash
  id username
  ```

- **`su`**: Substitute user identity.
  ```bash
  su - username
  ```

- **`sudo`**: Execute a command as another user (superuser by default).
  ```bash
  sudo command
  ```

- **`whoami`**: Print the current user ID and name.
  ```bash
  whoami
  ```
[Back to top](#categories)
## System Maintenance Tasks:
- **`cron`**: Schedule periodic background jobs.
  - Edit crontab:
    ```bash
    crontab -e
    ```
  - List crontab:
    ```bash
    crontab -l
    ```

- **`at`**: Schedule commands to be executed at a later time.
  ```bash
  at 2pm tomorrow
  at> command_to_run
  ```

- **`systemctl`**: Control the systemd system and service manager.
  ```bash
  systemctl status service
  systemctl start service
  systemctl stop service
  systemctl restart service
  systemctl enable service   # Enable service on boot
  systemctl disable service  # Disable service on boot
  ```

- **`journalctl`**: Query and display messages from the journal.
  ```bash
  journalctl -xe
  journalctl -u service_name
  ```

- **`service`**: Run a System V init script.
  ```bash
  service service_name start
  service service_name stop
  service service_name restart
  ```

- **`shutdown`**: Bring the system down.
  ```bash
  shutdown -h now      # Halt the system
  shutdown -r now      # Reboot the system
  shutdown -h +10 "Shutdown in 10 minutes"  # Scheduled shutdown
  ```

- **`reboot`**: Reboot the system.
  ```bash
  reboot
  ```

- **`halt`**: Halt the system.
  ```bash
  halt
  ```

- **`mount`**: Mount a file system.
  ```bash
  mount /dev/sda1 /mnt
  mount -o loop /path/to/image.iso /mnt
  ```

- **`umount`**: Unmount a file system.
  ```bash
  umount /mnt
  ```

- **`fsck`**: File system consistency check and repair.
  ```bash
  fsck /dev/sda1
  ```
[Back to top](#categories)
## Package Management (distribution-dependent):

### Debian-based Systems (e.g., Ubuntu):
- **`apt-get`**: APT package handling utility.
  ```bash
  apt-get update             # Update package lists
  apt-get upgrade            # Upgrade all packages
  apt-get install package    # Install package
  apt-get remove package     # Remove package
  apt-get autoremove         # Remove unused packages
  ```

- **`apt`**: Advanced Package Tool.
  ```bash
  apt update                 # Update package lists
  apt upgrade                # Upgrade all packages
  apt install package        # Install package
  apt remove package         # Remove package
  apt search package         # Search for package
  apt show package           # Show package details
  ```

- **`dpkg`**: Debian package manager.
  ```bash
  dpkg -i package.deb        # Install .deb package
  dpkg -r package            # Remove package
  dpkg -l                    # List installed packages
  ```

### Red Hat-based Systems (e.g., CentOS, Fedora):
- **`yum`**: Package manager for RPM-based distributions.
  ```bash
  yum update                 # Update all packages
  yum install package        # Install package
  yum remove package         # Remove package
  yum list installed         # List installed packages
  ```

- **`dnf`**: Dandified YUM, the next-generation version of YUM.
  ```bash
  dnf update                 # Update all packages
  dnf install package        # Install package
  dnf remove package         # Remove package
  dnf list installed         # List installed packages
  ```

- **`rpm`**: RPM package manager.
  ```bash
  rpm -ivh package.rpm       # Install .rpm package
  rpm -e package             # Remove package
  rpm -qa                    # List installed packages
  ```

### Arch-based Systems:
- **`pacman`**: Package manager utility for Arch Linux.
  ```bash
  pacman -Syu                # Update system and packages
  pacman -S package          # Install package
  pacman -R package          # Remove package
  pacman -Ss package         # Search for package
  ```
[Back to top](#categories)
## Compression and Archive Utilities:
- **`tar`**: Archiving utility.
  ```bash
  tar -cvf archive.tar file1 file2       # Create tar archive
  tar -xvf archive.tar                   # Extract tar archive
  tar -czvf archive.tar.gz file1 file2   # Create gzipped tar archive
  tar -xzvf archive.tar.gz               # Extract gzipped tar archive
  ```

- **`gzip`**: Compress

 files.
  ```bash
  gzip file.txt                # Compress file
  gunzip file.txt.gz           # Decompress file
  ``

[Back to top](#categories)
## Compression and Archive Utilities (continued):

- **`bzip2`**: Compress files using the Burrows-Wheeler block sorting text compression algorithm.

  ```bash
  bzip2 file.txt             # Compress file
  bunzip2 file.txt.bz2       # Decompress file
  ```

- **`xz`**: Compress files using LZMA/LZMA2 compression algorithms.
  ```bash
  xz file.txt                # Compress file
  unxz file.txt.xz           # Decompress file
  ```

- **`zip`**: Package and compress files.
  ```bash
  zip archive.zip file1 file2   # Create zip archive
  unzip archive.zip             # Extract zip archive
  ```

- **`7z`**: High compression ratio file archiver.
  ```bash
  7z a archive.7z file1 file2   # Create 7z archive
  7z x archive.7z               # Extract 7z archive
  ```

- **`rar`**: Archive manager.
  ```bash
  rar a archive.rar file1 file2   # Create rar archive
  unrar x archive.rar             # Extract rar archive
  ```

- **`ar`**: Create, modify, and extract from archives.
  ```bash
  ar rcs archive.a file1 file2    # Create archive
  ar x archive.a                  # Extract archive
  ```

- **`zcat`**: View compressed file content.
  ```bash
  zcat file.txt.gz               # View gzipped file content
  ```

- **`zgrep`**: Search within compressed files.
  ```bash
  zgrep "pattern" file.txt.gz    # Search pattern in gzipped file
  ```

- **`zless`**: View compressed file content with less.
  ```bash
  zless file.txt.gz              # View gzipped file content with less
  ```

- **`zmore`**: View compressed file content with more.
  ```bash
  zmore file.txt.gz              # View gzipped file content with more
  ```

- **`lzma`**: Compress files using the LZMA algorithm.
  ```bash
  lzma file.txt                 # Compress file
  unlzma file.txt.lzma          # Decompress file
  ```

- **`lzop`**: Fast compression utility.
  ```bash
  lzop file.txt                 # Compress file
  unlzop file.txt.lzo           # Decompress file
  ```

- **`tar` + Compression**: Combining `tar` with compression utilities.
  ```bash
  tar -cvf archive.tar file1 file2   # Create tar archive
  tar -czvf archive.tar.gz file1     # Create gzip compressed tar archive
  tar -cjvf archive.tar.bz2 file1    # Create bzip2 compressed tar archive
  tar -cJvf archive.tar.xz file1     # Create xz compressed tar archive
  tar -cvzf archive.tar.lzop file1   # Create lzop compressed tar archive
  ```
[Back to top](#categories)
## Disk Usage and Disk Management:
- **`df`**: Report file system disk space usage.
  ```bash
  df -h                      # Human-readable format
  df -T                      # Show file system type
  ```

- **`du`**: Estimate file space usage.
  ```bash
  du -sh *                   # Human-readable total for each item
  du -ch                     # Human-readable cumulative sizes
  ```

- **`lsblk`**: List information about block devices.
  ```bash
  lsblk
  ```

- **`fdisk`**: Partition table manipulator for Linux.
  ```bash
  fdisk /dev/sda             # Interactive partition table editor
  fdisk -l                   # List partition tables
  ```

- **`parted`**: A partition manipulation program.
  ```bash
  parted /dev/sda            # Interactive mode
  parted /dev/sda print      # Print partition table
  ```

- **`mkfs`**: Build a Linux file system.
  ```bash
  mkfs.ext4 /dev/sda1        # Create ext4 file system
  ```

- **`blkid`**: Locate/print block device attributes.
  ```bash
  blkid                      # Display block device UUIDs
  ```

- **`fsck`**: File system consistency check and repair.
  ```bash
  fsck /dev/sda1             # Check and repair file system
  ```

- **`mount`**: Mount a file system.
  ```bash
  mount /dev/sda1 /mnt       # Mount a file system
  mount -o loop image.iso /mnt  # Mount an ISO image
  ```

- **`umount`**: Unmount file systems.
  ```bash
  umount /mnt                # Unmount a file system
  ```

- **`swap`**: Swap file and memory management.
  ```bash
  swapon /dev/sda2           # Enable swap space
  swapoff /dev/sda2          # Disable swap space
  swapon -s                  # Display swap usage
  ```

- **`tune2fs`**: Adjust tunable file system parameters.
  ```bash
  tune2fs -l /dev/sda1       # List file system parameters
  ```

- **`e2fsck`**: Check a Linux ext2/ext3/ext4 file system.
  ```bash
  e2fsck /dev/sda1           # Check and repair file system
  ```
[Back to top](#categories)
## Advanced Disk Usage and Management:
- **`lvm`**: Logical Volume Manager commands.
  ```bash
  pvcreate /dev/sda1         # Create a physical volume
  vgcreate my_vg /dev/sda1   # Create a volume group
  lvcreate -n my_lv -L 10G my_vg  # Create a logical volume
  lvextend -L +5G /dev/my_vg/my_lv  # Extend a logical volume
  lvreduce -L -5G /dev/my_vg/my_lv  # Reduce a logical volume
  lvremove /dev/my_vg/my_lv  # Remove a logical volume
  ```

- **`cryptsetup`**: LUKS disk encryption.
  ```bash
  cryptsetup luksFormat /dev/sda1       # Format a disk with LUKS
  cryptsetup luksOpen /dev/sda1 mycrypt # Open a LUKS encrypted disk
  cryptsetup luksClose mycrypt          # Close a LUKS encrypted disk
  ```
[Back to top](#categories)
## Monitoring and Performance Tuning:
- **`top`**: Display and update sorted information about processes.
  ```bash
  top
  ```

- **`htop`**: Interactive process viewer.
  ```bash
  htop
  ```

- **`iostat`**: Report CPU and I/O statistics.
  ```bash
  iostat
  ```

- **`vmstat`**: Report virtual memory statistics.
  ```bash
  vmstat
  ```

- **`sar`**: Collect, report, or save system activity information.
  ```bash
  sar -u 1 10                 # CPU usage at 1 second intervals, 10 times
  sar -r 1 10                 # Memory usage at 1 second intervals, 10 times
  ```

- **`dstat`**: Versatile resource statistics.
  ```bash
  dstat
  ```

- **`nmon`**: Performance monitor for Linux.
  ```bash
  nmon
  ```

- **`mpstat`**: Report CPU usage per processor.
  ```bash
  mpstat -P ALL 1 5           # Per-processor statistics every second, 5 times
  ```

- **`perf`**: Performance analysis tool.
  ```bash
  perf stat ls                # Performance statistics for the `ls` command
  perf record -a -g           # Record performance data for all CPUs
  ```
[Back to top](#categories)
## Security and Access Control:
- **`iptables`**: Administration tool for IPv4 packet filtering and NAT.
  ```bash
  iptables -L                 # List rules
  iptables -A INPUT -p tcp --dport 22 -j ACCEPT  # Allow SSH
  iptables -A INPUT -p tcp --dport 80 -j ACCEPT  # Allow HTTP
  iptables -D INPUT -p tcp --dport 80 -j ACCEPT  # Remove HTTP rule
  ```

- **`ufw`**: Uncomplicated Firewall, a frontend for `iptables`.
  ```bash
  ufw enable                  # Enable the firewall
  ufw disable                 # Disable the firewall
  ufw allow 22                # Allow SSH
  ufw deny 80                 # Deny HTTP
  ufw status                  # Display current status
  ```

- **`firewalld`**: A dynamic firewall management tool.
  ```bash
  firewall-cmd --state        # Check firewall state
  firewall-cmd --zone=public --add-service=http  # Allow HTTP
  firewall-cmd --zone=public --remove-service=http  # Remove HTTP
  ```

- **`fail2ban`**:

 Ban IPs with multiple failed login attempts.
  ```bash
  fail2ban-client status      # Display fail2ban status
  fail2ban-client start       # Start fail2ban
  fail2ban-client stop        # Stop fail2ban
  ```

- **`semanage`**: SELinux policy management.
  ```bash
  semanage fcontext -a -t httpd_sys_content_t "/web(/.*)?"  # Add SELinux context
  ```

- **`setsebool`**: Set SELinux boolean value.
  ```bash
  setsebool httpd_can_network_connect on  # Allow Apache network connections
  ```

- **`ausearch`**: Query audit daemon logs.
  ```bash
  ausearch -m AVC,USER_AVC -ts today  # Search SELinux denials
  ```

- **`auditctl`**: Control the state of the audit system.
  ```bash
  auditctl -l                   # List current audit rules
  auditctl -w /etc/passwd -p wa  # Audit changes to /etc/passwd
  ```
[Back to top](#categories)
## Virtualization and Container Management:
- **`docker`**: A platform for developing, shipping, and running applications in containers.
  ```bash
  docker ps                    # List running containers
  docker images                # List images
  docker pull image_name       # Pull an image
  docker run -d image_name     # Run a container
  docker exec -it container_id /bin/bash  # Access running container
  docker stop container_id     # Stop a container
  docker rm container_id       # Remove a container
  ```

- **`kubectl`**: Command-line tool for controlling Kubernetes clusters.
  ```bash
  kubectl get pods             # List pods
  kubectl get services         # List services
  kubectl apply -f file.yaml   # Apply configuration from a file
  kubectl exec -it pod_name -- /bin/bash  # Access pod shell
  ```

- **`virsh`**: Command-line interface for managing KVM-based virtual machines.
  ```bash
  virsh list --all             # List all VMs
  virsh start vm_name          # Start a VM
  virsh shutdown vm_name       # Shutdown a VM
  virsh destroy vm_name        # Force shutdown a VM
  virsh console vm_name        # Access VM console
  ```

- **`vagrant`**: Tool for building and managing virtualized environments.
  ```bash
  vagrant init                 # Initialize Vagrant environment
  vagrant up                   # Start and provision the Vagrant environment
  vagrant halt                 # Stop the Vagrant environment
  vagrant ssh                  # SSH into the Vagrant environment
  ```
[Back to top](#categories)
## Miscellaneous Commands:
- **`alias`**: Create an alias for a command.
  ```bash
  alias ll='ls -la'
  unalias ll
  ```

- **`echo`**: Display a line of text.
  ```bash
  echo "Hello, World!"
  ```

- **`date`**: Display or set the system date and time.
  ```bash
  date
  date -s "2024-06-25 10:00:00"
  ```

- **`cal`**: Display a calendar.
  ```bash
  cal
  ```

- **`bc`**: An arbitrary precision calculator language.
  ```bash
  bc
  ```

- **`shutdown`**: Bring the system down in a secure way.
  ```bash
  shutdown -h now             # Halt the system immediately
  shutdown -r now             # Reboot the system immediately
  ```

- **`reboot`**: Reboot the system.
  ```bash
  reboot
  ```

- **`clear`**: Clear the terminal screen.
  ```bash
  clear
  ```

- **`history`**: Command history management.
  ```bash
  history                     # Display command history
  history -c                  # Clear command history
  ```

- **`whoami`**: Display the current user.
  ```bash
  whoami
  ```

- **`uname`**: Print system information.
  ```bash
  uname -a                    # All system information
  uname -r                    # Kernel version
  ```

- **`uptime`**: Show how long the system has been running.
  ```bash
  uptime
  ```

- **`dmesg`**: Print or control the kernel ring buffer.
  ```bash
  dmesg
  ```

- **`env`**: Show the environment variables.
  ```bash
  env
  ```

- **`printenv`**: Print all or part of environment.
  ```bash
  printenv
  ```

- **`export`**: Set environment variables.
  ```bash
  export VAR=value
  ```

- **`source`**: Read and execute commands from a file.
  ```bash
  source filename
  ```

- **`hostname`**: Show or set the system's hostname.
  ```bash
  hostname                    # Show hostname
  hostname newhostname        # Set hostname
  ```

- **`sleep`**: Delay for a specified amount of time.
  ```bash
  sleep 10                    # Sleep for 10 seconds
  ```

- **`watch`**: Execute a program periodically, showing output fullscreen.
  ```bash
  watch df -h                 # Watch disk space usage
  ```

- **`xargs`**: Build and execute command lines from standard input.
  ```bash
  echo "file1 file2 file3" | xargs rm  # Remove multiple files
  ```

- **`tee`**: Read from standard input and write to standard output and files.
  ```bash
  ls -l | tee filelist.txt    # List directory and save to file
  ```

- **`yes`**: Output a string repeatedly until killed.
  ```bash
  yes "y"                     # Repeat "y" until interrupted
  ```

- **`seq`**: Print a sequence of numbers.
  ```bash
  seq 1 10                    # Print numbers from 1 to 10
  ```

- **`bc`**: An arbitrary precision calculator language.
  ```bash
  echo "scale=2; 3/8" | bc    # Calculate with precision
  ```

- **`nc`**: Netcat, the Swiss Army knife of networking.
  ```bash
  nc -zv host port            # Check if port is open
  nc -l -p port               # Listen on a port
  ```
[Back to top](#categories)
## Text Processing Utilities:
- **`awk`**: Pattern scanning and processing language.
  ```bash
  awk '{print $1}' file.txt   # Print first field of each line
  awk -F, '{print $1}' file.csv  # Print first field of a comma-separated file
  ```

- **`sed`**: Stream editor for filtering and transforming text.
  ```bash
  sed 's/old/new/g' file.txt  # Replace all instances of 'old' with 'new'
  sed -n '1,5p' file.txt      # Print lines 1 to 5
  ```

- **`grep`**: Print lines matching a pattern.
  ```bash
  grep "pattern" file.txt     # Search for pattern in file
  grep -r "pattern" dir/      # Search recursively in directory
  ```

- **`cut`**: Remove sections from each line of files.
  ```bash
  cut -d',' -f1 file.csv      # Cut first field of a comma-separated file
  ```

- **`paste`**: Merge lines of files.
  ```bash
  paste file1 file2           # Merge lines side by side
  ```

- **`sort`**: Sort lines of text files.
  ```bash
  sort file.txt               # Sort lines alphabetically
  sort -n file.txt            # Sort lines numerically
  ```

- **`uniq`**: Report or omit repeated lines.
  ```bash
  uniq file.txt               # Remove duplicate lines
  uniq -c file.txt            # Count duplicate lines
  ```

- **`tr`**: Translate or delete characters.
  ```bash
  echo "hello" | tr 'a-z' 'A-Z'  # Convert to uppercase
  echo "hello" | tr -d 'aeiou'  # Remove vowels
  ```

- **`wc`**: Print newline, word, and byte counts for each file.
  ```bash
  wc file.txt                 # Count lines, words, and bytes
  wc -l file.txt              # Count lines
  ```

- **`head`**: Output the first part of files.
  ```bash
  head -n 10 file.txt         # First 10 lines of file
  ```

- **`tail`**: Output the last part of files.
  ```bash
  tail -n 10 file.txt         # Last 10 lines of file
  ```

- **`split`**: Split a file into pieces.
  ```bash
  split -l 1000 file.txt      # Split into 1000-line pieces
  ```

- **`join`**: Join lines of two files on a common field.
  ```bash
  join file1.txt file

2.txt    # Join files on first field
  ```

- **`diff`**: Compare files line by line.
  ```bash
  diff file1.txt file2.txt    # Show differences between files
  ```

- **`cmp`**: Compare two files byte by byte.
  ```bash
  cmp file1 file2             # Compare files
  ```

- **`xxd`**: Make a hexdump or do the reverse.
  ```bash
  xxd file.bin                # Hexdump file
  xxd -r file.hex             # Reverse hexdump
  ```

- **`strings`**: Extract printable strings from binary files.
  ```bash
  strings file.bin            # Extract strings from binary file
  ```

- **`nl`**: Number lines of files.
  ```bash
  nl file.txt                 # Number the lines
  ```

- **`fmt`**: Simple optimal text formatter.
  ```bash
  fmt file.txt                # Format text
  ```

- **`pr`**: Convert text files for printing.
  ```bash
  pr file.txt                 # Paginate file for printing
  ```

- **`expand`**: Convert tabs to spaces.
  ```bash
  expand file.txt             # Convert tabs to spaces
  ```

- **`unexpand`**: Convert spaces to tabs.
  ```bash
  unexpand file.txt           # Convert spaces to tabs
  ```

- **`tac`**: Concatenate and print files in reverse.
  ```bash
  tac file.txt                # Print file in reverse
  ```

- **`rev`**: Reverse lines characterwise.
  ```bash
  rev file.txt                # Reverse lines in file
  ```

- **`column`**: Columnate lists.
  ```bash
  column -t file.txt          # Format text into columns
  ```
[Back to top](#categories)
## Development and Debugging:
- **`gcc`**: The GNU Compiler Collection.
  ```bash
  gcc -o output file.c        # Compile C program
  gcc -o output file.c -Wall  # Compile with warnings
  ```

- **`g++`**: The GNU C++ Compiler.
  ```bash
  g++ -o output file.cpp      # Compile C++ program
  ```

- **`make`**: Build automation tool.
  ```bash
  make                        # Build project
  make clean                  # Clean build files
  ```

- **`cmake`**: Cross-platform build system generator.
  ```bash
  cmake .                     # Generate build files in current directory
  cmake --build .             # Build project
  ```

- **`gdb`**: The GNU Debugger.
  ```bash
  gdb ./program               # Debug program
  gdb --args ./program arg1   # Debug program with arguments
  ```

- **`strace`**: Trace system calls and signals.
  ```bash
  strace -o strace.log ./program  # Trace program and log to file
  ```

- **`ltrace`**: Trace library calls.
  ```bash
  ltrace ./program            # Trace program's library calls
  ```

- **`valgrind`**: Memory debugging and profiling tool.
  ```bash
  valgrind ./program          # Run program with Valgrind
  ```

- **`nm`**: List symbols from object files.
  ```bash
  nm file.o                   # List symbols in object file
  ```

- **`objdump`**: Display information from object files.
  ```bash
  objdump -d file.o           # Disassemble object file
  ```

- **`readelf`**: Display information about ELF files.
  ```bash
  readelf -h file.o           # Display ELF header
  ```

- **`ldd`**: Print shared library dependencies.
  ```bash
  ldd ./program               # List shared libraries used by program
  ```

- **`git`**: Distributed version control system.
  ```bash
  git init                    # Initialize a new Git repository
  git clone url               # Clone a repository
  git add file.txt            # Add file to staging area
  git commit -m "message"     # Commit changes
  git push                    # Push changes to remote repository
  git pull                    # Pull changes from remote repository
  ```

- **`svn`**: Apache Subversion client.
  ```bash
  svn checkout url            # Checkout a repository
  svn add file.txt            # Add file to version control
  svn commit -m "message"     # Commit changes
  svn update                  # Update working copy
  ```

- **`hg`**: Mercurial distributed version control system.
  ```bash
  hg init                     # Initialize a new Mercurial repository
  hg clone url                # Clone a repository
  hg add file.txt             # Add file to version control
  hg commit -m "message"      # Commit changes
  hg push                     # Push changes to remote repository
  ```

- **`cvs`**: Concurrent Versions System client.
  ```bash
  cvs checkout module         # Checkout a module
  cvs add file.txt            # Add file to version control
  cvs commit -m "message"     # Commit changes
  cvs update                  # Update working copy
  ```

- **`make`**: Build automation tool.
  ```bash
  make                        # Build project using Makefile
  make clean                  # Clean build files
  ```

- **`cmake`**: Cross-platform build system generator.
  ```bash
  cmake .                     # Generate build files in current directory
  cmake --build .             # Build project
  ```
[Back to top](#categories)
## SSH and Remote Management:
- **`ssh`**: OpenSSH client for secure remote login.
  ```bash
  ssh user@host               # Connect to host as user
  ssh -i keyfile user@host    # Connect using a specific key
  ```

- **`scp`**: Securely copy files between hosts.
  ```bash
  scp file.txt user@host:/path/to/destination  # Copy file to remote host
  scp user@host:/path/to/file.txt ./destination  # Copy file from remote host
  ```

- **`rsync`**: Fast, versatile, remote (and local) file-copying tool.
  ```bash
  rsync -avz source/ user@host:/path/to/destination  # Sync directories
  rsync -avz user@host:/path/to/source/ destination  # Sync from remote host
  ```

- **`sftp`**: Secure file transfer program.
  ```bash
  sftp user@host               # Connect to SFTP server
  sftp> put file.txt           # Upload file
  sftp> get file.txt           # Download file
  ```

- **`screen`**: Terminal multiplexer.
  ```bash
  screen                       # Start a new session
  screen -r                    # Reattach to a session
  screen -ls                   # List all sessions
  ```

- **`tmux`**: Terminal multiplexer.
  ```bash
  tmux                         # Start a new session
  tmux attach                  # Reattach to a session
  tmux list-sessions           # List all sessions
  ```

- **`vnc`**: Virtual Network Computing.
  ```bash
  vncserver                    # Start a VNC server
  vncviewer host:display       # Connect to a VNC server
  ```

- **`mtr`**: Network diagnostic tool combining `ping` and `traceroute`.
  ```bash
  mtr google.com               # Run MTR to a host
  ```

- **`nc`**: Netcat, the Swiss Army knife of networking.
  ```bash
  nc -zv host port             # Check if port is open
  nc -l -p port                # Listen on a port
  ```

- **`telnet`**: User interface to the TELNET protocol.
  ```bash
  telnet host port             # Connect to a host and port
  ```
[Back to top](#categories)
## Useful Shortcuts and Tips:
- **Tab Completion**: Automatically complete file names, commands, etc.
  ```bash
  ls /usr/lo<TAB>               # Autocomplete to /usr/local/
  ```

- **Command History**: Use the up and down arrow keys to navigate command history.
  ```bash
  !!                           # Repeat the last command
  !n                           # Repeat the nth command in history
  !grep                        # Repeat the last command starting with 'grep'
  ```

- **Keyboard Shortcuts**:
  - `Ctrl+C`: Cancel current command.
  - `Ctrl+Z`: Suspend current command.
  - `Ctrl+A`: Move cursor to the beginning of the line.
  - `Ctrl+E`: Move cursor to the end of the line.
  - `Ctrl+R`: Reverse search command history.
  - `Ctrl+D`: Log out of the current session.

```

This comprehensive list covers a wide range of commands for various tasks in Linux. Adjust as needed for your specific use case or distribution.


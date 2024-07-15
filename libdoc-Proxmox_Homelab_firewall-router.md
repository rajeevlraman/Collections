---
title: Proxmox_Homelab_firewall-router
description: Proxmox_Homelab_firewall-router
layout: libdoc/page

#LibDoc specific below
category: Features
order: 108
#unlisted: true
---
* 
{:toc}


# Home Network Setup Guide

## Overview

This guide will help you set up:
1. **PfSense Firewall/Router** for network security.
2. **Pi-hole** for DNS and ad-blocking.
3. **OpenMediaVault (OMV)** for Network Attached Storage (NAS).

### Hardware Requirements

- **Coolermaster PC** with AMD A6-6400K APU @ 3.9GHz, 8GB RAM
- **1 SSD** (128GB) for PfSense and Pi-hole
- **2 HDDs** (1TB each) for NAS

### Network Diagram

```plaintext
[Internet] <---> [PfSense Firewall/Router] <---> [Switch] <---> [Devices]
                                              \---> [Pi-hole DNS]
                                              \---> [OpenMediaVault NAS]
```



## Step 1: Installing and Configuring PfSense

### 1.1 Download PfSense

- Visit the [PfSense download page](https://www.pfsense.org/download/).
- Select the appropriate architecture and version for your hardware.
- Download the installer (ISO image).

### 1.2 Create a Bootable USB Drive

- Use tools like **Rufus** (Windows) or **balenaEtcher** (Mac/Linux) to create a bootable USB drive from the ISO image.

### 1.3 Install PfSense

1. **Insert the bootable USB** into your Coolermaster PC and boot from it.
2. **Follow the on-screen instructions** to install PfSense on the SSD.
   - Choose the default options unless you have specific needs.
   - Set the WAN (internet-facing) and LAN (local network) interfaces.

### 1.4 Initial Configuration

1. **Access the web interface**: Connect a computer to the LAN port of the PfSense device and go to `http://192.168.1.1` in a web browser.
2. **Login** with default credentials (`admin` / `pfsense`).
3. **Follow the setup wizard** to configure basic settings:
   - Change the LAN IP address if necessary.
   - Set up the WAN interface.
   - Create an admin password.

### 1.5 Enable DHCP

1. **Navigate to**: Services > DHCP Server.
2. **Enable DHCP** on the LAN interface.
3. **Configure the DHCP range**: Set the range of IP addresses to be assigned to clients.

### 1.6 Secure PfSense

- **Change the default ports** for web interface access.
- **Set up firewall rules** to restrict unnecessary access.



## Step 2: Installing and Configuring Pi-hole

### 2.1 Prepare the System

1. **Ensure the system is up-to-date** by running:
   ```bash
   sudo apt-get update
   sudo apt-get upgrade
   ```

### 2.2 Install Pi-hole

1. **Run the installation script**:
   ```bash
   curl -sSL https://install.pi-hole.net | bash
   ```

2. **Follow the prompts** to configure Pi-hole:
   - Choose `eth0` as the interface (assuming it's your main network interface).
   - Select the default upstream DNS provider or choose your own.
   - Set the IP address to static (recommended for stability).

### 2.3 Configure DNS

1. **Point your devices to use Pi-hole** as their DNS server:
   - Set the Pi-hole IP as the DNS server in your router's DHCP settings (recommended).
   - Or, set it manually on each device.

2. **Update PfSense to use Pi-hole** as the DNS resolver:
   - Go to System > General Setup in PfSense.
   - Add the Pi-hole IP address in the DNS server list and uncheck `Allow DNS server list to be overridden by DHCP/PPP on WAN`.

### 2.4 Configure Ad-blocking

1. **Access the Pi-hole admin interface**: Go to `http://pi.hole/admin` or `http://<Pi-hole IP>/admin`.
2. **Login** with the password set during installation.
3. **Enable ad lists** in Group Management > Adlists.



## Step 3: Installing and Configuring OpenMediaVault (OMV)

### 3.1 Download OpenMediaVault

- Visit the [OpenMediaVault download page](https://www.openmediavault.org/download.html).
- Download the appropriate ISO for your hardware.

### 3.2 Create a Bootable USB Drive

- Use tools like **Rufus** or **balenaEtcher** to create a bootable USB drive from the OMV ISO image.

### 3.3 Install OpenMediaVault

1. **Insert the bootable USB** into the PC and boot from it.
2. **Follow the installation instructions** to install OMV on one of the HDDs.
   - During installation, select the disk where OMV will be installed.
   - Use the other HDD for data storage.

### 3.4 Initial Configuration

1. **Access the OMV web interface**: Go to `http://<OMV IP>` in a web browser.
2. **Login** with the default credentials (`admin` / `openmediavault`).

### 3.5 Configure Storage

1. **Navigate to**: Storage > Disks.
   - **Initialize the disks** if they are not already initialized.
2. **Go to**: Storage > File Systems.
   - **Create and mount file systems** on the data HDDs.

### 3.6 Setup Shared Folders

1. **Go to**: Access Rights Management > Shared Folders.
   - **Create shared folders** for data storage.
2. **Assign permissions** to these folders as needed.

### 3.7 Enable SMB/CIFS for Windows Shares

1. **Navigate to**: Services > SMB/CIFS.
   - **Enable the service**.
   - **Add the shared folders** to the service.

### 3.8 Secure OMV

- **Change the default admin password**.
- **Set up user accounts** with appropriate permissions.

---

## Summary

You now have a home network set up with:
- **PfSense** for robust firewall and routing.
- **Pi-hole** for DNS and ad-blocking.
- **OpenMediaVault** for network-attached storage.

Remember to regularly update your systems to keep them secure and maintain backups of your configurations.

---

## Useful Links

- [PfSense Documentation](https://docs.netgate.com/pfsense/en/latest/)
- [Pi-hole Documentation](https://docs.pi-hole.net/)
- [OpenMediaVault Documentation](https://openmediavault.readthedocs.io/en/latest/)

```

To create a RAID 0 array with two 1TB disks in Proxmox, you’ll use the `mdadm` tool, which is a Linux utility for managing software RAID arrays. Here's a step-by-step guide in Markdown format:


# Creating RAID 0 with Two 1TB Disks in Proxmox

## Prerequisites

- **Proxmox VE** installed and running.
- **Two 1TB disks** available for RAID 0 configuration.

## Steps to Create RAID 0

### Step 1: Identify the Disks

1. **Open a terminal** or SSH into your Proxmox server.
2. **List all disks** to identify the 1TB disks:
   ```bash
   lsblk
   ```
   - Look for the 1TB disks (e.g., `/dev/sdb` and `/dev/sdc`).

### Step 2: Install `mdadm` (if not already installed)

1. **Install `mdadm`** package:
   ```bash
   apt-get update
   apt-get install mdadm
   ```

### Step 3: Create the RAID 0 Array

1. **Create the RAID 0 array** using `mdadm`:
   ```bash
   mdadm --create --verbose /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc
   ```
   - `/dev/md0` is the RAID array device.
   - `--level=0` specifies RAID 0.
   - `--raid-devices=2` indicates two disks.
   - `/dev/sdb` and `/dev/sdc` are the 1TB disks.

2. **Monitor the RAID creation process**:
   ```bash
   cat /proc/mdstat
   ```

### Step 4: Create a File System on the RAID Array

1. **Create a file system** (e.g., ext4) on the new RAID array:
   ```bash
   mkfs.ext4 /dev/md0
   ```

### Step 5: Mount the RAID Array

1. **Create a mount point**:
   ```bash
   mkdir /mnt/raid0
   ```

2. **Mount the RAID array**:
   ```bash
   mount /dev/md0 /mnt/raid0
   ```

3. **Verify the RAID array is mounted**:
   ```bash
   df -h
   ```

### Step 6: Configure Auto-Mount on Boot

1. **Get the UUID** of the RAID array:
   ```bash
   blkid /dev/md0
   ```
   - Note the `UUID` (e.g., `UUID="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"`).

2. **Edit the `/etc/fstab` file** to add the RAID array for auto-mount:
   ```bash
   nano /etc/fstab
   ```
   - Add the following line at the end of the file:
     ```plaintext
     UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /mnt/raid0 ext4 defaults 0 0
     ```

3. **Save and exit** the file.

4. **Test the `fstab` configuration**:
   ```bash
   mount -a
   ```
   - Ensure there are no errors.

### Step 7: Verify RAID 0 Array Status

1. **Check the RAID array status**:
   ```bash
   mdadm --detail /dev/md0
   ```

---

## Summary

You now have a RAID 0 array set up with two 1TB disks on your Proxmox server. This array can be used for high-speed data storage, though it does not provide redundancy. Be sure to back up important data stored on this array.

---

## Useful Commands

- **List RAID arrays**:
  ```bash
  mdadm --detail --scan
  ```

- **Monitor RAID arrays**:
  ```bash
  watch cat /proc/mdstat
  ```

- **Stop a RAID array** (if needed):
  ```bash
  mdadm --stop /dev/md0
  ```

- **Remove a RAID array** (if needed):
  ```bash
  mdadm --remove /dev/md0
  ```

---

## Useful Links

- [Proxmox VE Documentation](https://pve.proxmox.com/pve-docs/)
- [mdadm Manual](https://man7.org/linux/man-pages/man8/mdadm.8.html)



### Additional Notes

- **Data Safety**: RAID 0 offers no redundancy. Any disk failure will result in data loss. Ensure you have backups if you choose RAID 0.
- **Performance**: RAID 0 can provide increased performance but is not suitable for data critical storage due to the lack of fault tolerance.
- **Auto-Mount**: Editing `/etc/fstab` ensures that the RAID array mounts automatically at boot.

If you have any specific questions or run into issues during the process, feel free to ask!

### Additional Notes

- **PfSense and Pi-hole**: Consider using the SSD for PfSense and installing Pi-hole on the same SSD if it’s running on a separate OS. Alternatively, use a separate low-power device like a Raspberry Pi for Pi-hole.
- **Network Configuration**: Ensure your network configuration is consistent and does not create IP conflicts, especially when setting static IPs for Pi-hole and OMV.
- **Backups**: Regularly backup your configuration files for PfSense, Pi-hole, and OMV to avoid data loss during updates or hardware failures.

If you need more specific details or have any questions during the setup process, feel free to ask!

```bash
root@dasherhomelab:~# lsblk

NAME                                       MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda                                          8:0    0 119.2G  0 disk
├─sda1                                       8:1    0  1007K  0 part
├─sda2                                       8:2    0     1G  0 part
└─sda3                                       8:3    0 118.2G  0 part
  ├─pve-swap                               252:0    0   7.2G  0 lvm  [SWAP]
  ├─pve-root                               252:1    0  39.8G  0 lvm  /
  ├─pve-data_tmeta                         252:10   0     1G  0 lvm
  │ └─pve-data-tpool                       252:13   0  54.5G  0 lvm
  │   ├─pve-data                           252:14   0  54.5G  1 lvm
  │   ├─pve-vm--100--state--FIRST--PF--30--03--2024
  │   │                                    252:15   0   4.5G  0 lvm
  │   └─pve-vm--100--disk--0               252:16   0    32G  0 lvm
  └─pve-data_tdata                         252:12   0  54.5G  0 lvm
    └─pve-data-tpool                       252:13   0  54.5G  0 lvm
      ├─pve-data                           252:14   0  54.5G  1 lvm
      ├─pve-vm--100--state--FIRST--PF--30--03--2024
      │                                    252:15   0   4.5G  0 lvm
      └─pve-vm--100--disk--0               252:16   0    32G  0 lvm
sdb                                          8:16   0 931.5G  0 disk
├─VM--disks-vm--110--disk--0               252:2    0   100G  0 lvm
├─VM--disks-vm--102--disk--0               252:3    0   100G  0 lvm
├─VM--disks-vm--101--disk--0               252:4    0   110G  0 lvm
├─VM--disks-vm--101--disk--1               252:5    0     4M  0 lvm
├─VM--disks-vm--101--disk--2               252:6    0     4M  0 lvm
├─VM--disks-vm--100--disk--0               252:7    0    32G  0 lvm
├─VM--disks-vm--107--disk--0               252:8    0    40G  0 lvm
├─VM--disks-vm--103--disk--0               252:9    0    32G  0 lvm
└─VM--disks-vm--108--disk--0               252:11   0    50G  0 lvm
sdc                                          8:32   0 931.5G  0 disk
└─sdc1                                       8:33   0 931.5G  0 part
```

It seems that `/dev/sdb` is not part of any logical volume or volume group, despite the initial appearance from the `lsblk` output. This simplifies the process. Given this, we can proceed directly with cleaning the partitions and preparing both disks for the RAID 0 setup.

Here are the detailed steps to clean `/dev/sdb` and `/dev/sdc`, ensuring they are ready for RAID configuration:

### Step 1: Confirm Current Partitions

Let's verify the partition structure for both disks (`/dev/sdb` and `/dev/sdc`) using `lsblk` and `fdisk`:

```bash
lsblk
fdisk -l /dev/sdb
fdisk -l /dev/sdc
```

This will show the current partition layout and help confirm that `/dev/sdb` and `/dev/sdc` are indeed unpartitioned or only have irrelevant partitions.

### Step 2: Delete Partitions on `/dev/sdb` and `/dev/sdc`

1. **Use `fdisk` to delete partitions on `/dev/sdb`**:

   ```bash
   fdisk /dev/sdb
   ```

   - Press `d` to delete a partition.
   - If prompted, choose the partition number to delete (likely `1`).
   - Repeat the delete step if there are multiple partitions.
   - Press `w` to write changes and exit.

2. **Repeat the process for `/dev/sdc`**:

   ```bash
   fdisk /dev/sdc
   ```

   - Again, press `d` to delete the partition.
   - If prompted, choose the partition number to delete.
   - Press `w` to write changes and exit.

### Step 3: Zero Out the Disks

Zeroing out the beginning of the disks ensures there is no residual data that could interfere with the RAID setup.

1. **Zero out the first few MBs on `/dev/sdb`**:

   ```bash
   dd if=/dev/zero of=/dev/sdb bs=1M count=10
   ```

2. **Zero out the first few MBs on `/dev/sdc`**:

   ```bash
   dd if=/dev/zero of=/dev/sdc bs=1M count=10
   ```

### Step 4: Verify Disk Cleanliness

Check the status of the disks to confirm they are clean and unallocated:

1. **List the block devices** to confirm the disks have no partitions:

   ```bash
   lsblk
   ```

   You should see `/dev/sdb` and `/dev/sdc` without any partitions listed under them.

### Step 5: Proceed with RAID 0 Setup

With the disks now clean and unallocated, you can proceed to create the RAID 0 array as follows:

```bash
mdadm --create --verbose /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc
```

Follow the detailed steps provided earlier for creating a file system on the RAID array, mounting it, and configuring it to auto-mount on boot.

### Additional Notes:

- **No Logical Volumes**: Since there were no logical volumes or volume groups found on `/dev/sdb`, we skip the steps related to `lvremove` and `vgremove`.
- **Disk Usage**: Ensure no active usage of `/dev/sdb` and `/dev/sdc` before proceeding with the RAID setup to avoid data loss.

### Final Checks:

1. **Confirm the RAID Array**:
   ```bash
   cat /proc/mdstat
   ```
   This command shows the status of the RAID arrays.

2. **Check RAID Details**:
   ```bash
   mdadm --detail /dev/md0
   ```

3. **Ensure RAID is properly created** and proceed with file system creation, mounting, and adding to `/etc/fstab`.


# codes for partitioning.
# Commands Used During Troubleshooting



# Comprehensive Command Table from Troubleshooting

## General Disk and Partition Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `lsblk`                                | Lists all block devices and their mount points       | `lsblk`                             |
| `fdisk -l /dev/sdb`                    | Lists partition table of the specified disk          | `fdisk -l /dev/sdb`                 |
| `fdisk -l /dev/sdc`                    | Lists partition table of the specified disk          | `fdisk -l /dev/sdc`                 |
| `wipefs -af /dev/sdb`                  | Removes all filesystem signatures from the disk      | `wipefs -af /dev/sdb`               |
| `wipefs /dev/sdb`                      | Lists filesystem signatures on the specified disk    | `wipefs /dev/sdb`                   |
| `dd if=/dev/zero of=/dev/sdb bs=1M count=10` | Zeroes out the first few megabytes of the disk      | `dd if=/dev/zero of=/dev/sdb bs=1M count=10` |

## LVM (Logical Volume Manager) Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `vgchange -an <vg_name>`               | Deactivates a volume group                           | `vgchange -an pve`                  |
| `lvdisplay /dev/sdb`                   | Displays information about logical volumes on the disk | `lvdisplay /dev/sdb`             |
| `pvremove /dev/sdb`                    | Removes a physical volume from LVM                   | `pvremove /dev/sdb`                 |
| `vgreduce <vg_name> /dev/sdb`          | Removes a physical volume from a volume group        | `vgreduce pve /dev/sdb`             |
| `lvremove /dev/pve/lvol0`              | Removes a logical volume                             | `lvremove /dev/pve/lvol0`           |
| `vgremove pve`                         | Removes a volume group                               | `vgremove pve`                      |
| `vgchange -ay`                         | Activates all volume groups                          | `vgchange -ay`                      |

## Partitioning and RAID Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `fdisk /dev/sdb`                       | Opens fdisk to create/delete partitions on the disk  | `fdisk /dev/sdb`                    |
| `n`                                    | Creates a new partition in `fdisk`                   | Use within `fdisk`                  |
| `w`                                    | Writes changes to disk and exits `fdisk`             | Use within `fdisk`                  |
| `mdadm --create /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc` | Creates a RAID 0 array with two disks | `mdadm --create /dev/md0 --level=0 --raid-devices=2 /dev/sdb /dev/sdc` |
| `mdadm --detail /dev/md0`              | Shows detailed information about a RAID array        | `mdadm --detail /dev/md0`           |

## Filesystem Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `mkfs.ext4 /dev/sdb1`                  | Formats a partition with ext4 filesystem             | `mkfs.ext4 /dev/sdb1`               |
| `mkfs.ext4 /dev/md0`                   | Formats a RAID device with ext4 filesystem           | `mkfs.ext4 /dev/md0`                |

## Mounting and Unmounting

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `mkdir /mnt/mydisk`                    | Creates a directory to be used as a mount point      | `mkdir /mnt/mydisk`                 |
| `mount /dev/sdb1 /mnt/mydisk`          | Mounts a partition to a specified directory          | `mount /dev/sdb1 /mnt/mydisk`       |
| `umount /dev/sdb1`                     | Unmounts a specified partition                       | `umount /dev/sdb1`                  |

## System Service Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `systemctl stop lvm2-monitor.service`  | Stops the LVM monitoring service                     | `systemctl stop lvm2-monitor.service` |
| `systemctl stop mdmonitor.service`     | Stops the RAID monitoring service                    | `systemctl stop mdmonitor.service`  |

## Process Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `lsof /dev/sdb`                        | Lists open files and processes using the disk        | `lsof /dev/sdb`                     |
| `kill -9 PID`                          | Forcefully terminates a process                      | `kill -9 1234`                      |

## Swap Management

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `swapoff -a`                           | Disables all swap partitions                         | `swapoff -a`                        |

## Checking and Verifying

| Command                                | Description                                          | Example                             |
|----------------------------------------|------------------------------------------------------|-------------------------------------|
| `lsblk`                                | Lists all block devices and their mount points       | `lsblk`                             |
| `fdisk -l /dev/sdb`                    | Lists partition table of the specified disk          | `fdisk -l /dev/sdb`                 |
| `wipefs /dev/sdb`                      | Lists filesystem signatures on the specified disk    | `wipefs /dev/sdb`                   |


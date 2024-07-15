---
title: Ansible_installation
description: Ansible_installation
layout: libdoc/page

#LibDoc specific below
category: Features
order: 96
#unlisted: true
---
* 
{:toc}

## Prerequisites

1. **Host System Requirements**:
   - A system with at least 2GB of RAM and 2 CPU cores (more if you plan to manage a large number of nodes).
   - Access to a network to manage nodes (virtual network for VirtualBox or Hyper-V).

2. **Supported Operating Systems**:
   - Ansible can be installed on various Linux distributions such as Ubuntu, CentOS, Fedora, and Debian.
   - It can also be installed on macOS, or even Windows Subsystem for Linux (WSL) on Windows.

## Installation and Setup on Ubuntu (as an example)

### Step 1: Prepare Your Virtual Machine

1. **Hyper-V Setup**:
   - Open Hyper-V Manager.
   - Create a new virtual machine.
   - Choose Ubuntu as the operating system.
   - Allocate at least 2GB of RAM and 20GB of disk space.
   - Configure the network settings to connect to your virtual network.

2. **VirtualBox Setup**:
   - Open VirtualBox.
   - Create a new virtual machine and choose "Linux" and "Ubuntu (64-bit)" as the type.
   - Allocate at least 2GB of RAM and 20GB of disk space.
   - Set up network settings to use "Bridged Adapter" or "NAT" with port forwarding for SSH access.

### Step 2: Install Ubuntu on the Virtual Machine

1. **Download the Ubuntu ISO**:
   - Go to the [Ubuntu downloads page](https://ubuntu.com/download).
   - Download the latest LTS (Long Term Support) version, such as Ubuntu 22.04 LTS.

2. **Install Ubuntu**:
   - Boot the VM with the downloaded ISO.
   - Follow the installation prompts to install Ubuntu.

### Step 3: Update Your System

After Ubuntu is installed, log in and update the package lists and upgrade installed packages:

```bash
sudo apt update
sudo apt upgrade -y
```

### Step 4: Install Ansible

1. **Install Required Dependencies**:
   - Ansible requires Python. You can install Python and other dependencies using the following commands:

   ```bash
   sudo apt install -y python3 python3-pip python3-venv
   ```

2. **Add Ansible PPA (Personal Package Archive)**:
   - To get the latest version of Ansible, add the official Ansible PPA:

   ```bash
   sudo apt-add-repository --yes --update ppa:ansible/ansible
   ```

3. **Install Ansible**:
   - Now, install Ansible:

   ```bash
   sudo apt install -y ansible
   ```

### Step 5: Verify Ansible Installation

To ensure Ansible is installed correctly, check the version:

```bash
ansible --version
```

You should see output similar to this:

```
ansible [core 2.14.1]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/user/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3.8/site-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Nov 26 2021, 20:14:08) [GCC 10.3.0]
```

### Step 6: Configure Ansible

1. **Set Up the Inventory File**:
   - By default, the inventory file is located at `/etc/ansible/hosts`. You can edit this file to define your managed nodes:

   ```bash
   sudo nano /etc/ansible/hosts
   ```

   - Add the IP addresses or hostnames of the machines you want to manage. For example:

   ```
   [webservers]
   192.168.1.10
   192.168.1.11

   [dbservers]
   192.168.1.20
   ```

2. **Configure SSH Access**:
   - Ansible uses SSH to communicate with managed nodes. Ensure SSH is installed and running on your target nodes:

   ```bash
   sudo apt install -y openssh-server
   sudo systemctl enable ssh
   sudo systemctl start ssh
   ```

   - Copy your SSH key to the managed nodes for passwordless authentication:

   ```bash
   ssh-copy-id user@192.168.1.10
   ssh-copy-id user@192.168.1.11
   ```

3. **Test Connectivity**:
   - Test if Ansible can connect to your managed nodes by running a ping test:

   ```bash
   ansible all -m ping
   ```

   - You should see output indicating success:

   ```
   192.168.1.10 | SUCCESS => {
       "changed": false,
       "ping": "pong"
   }
   ```

### Step 7: Create and Run a Simple Playbook

1. **Create a Playbook**:
   - Create a simple playbook file, for example, `site.yml`:

   ```yaml
   - hosts: webservers
     tasks:
       - name: Ensure Apache is installed
         apt:
           name: apache2
           state: present
   ```

2. **Run the Playbook**:
   - Execute the playbook with the following command:

   ```bash
   ansible-playbook site.yml
   ```

   - Ansible will connect to the hosts in the `webservers` group and ensure Apache is installed.

### Step 8: Advanced Configuration (Optional)

1. **Ansible Configuration File**:
   - Ansible's main configuration file is located at `/etc/ansible/ansible.cfg`. You can customize settings such as the default inventory file, SSH settings, and more.

2. **Using Roles and Playbooks**:
   - For more complex automation, consider organizing your tasks into roles and using playbooks to define the order of execution.

3. **Using Dynamic Inventory**:
   - If you're managing a cloud environment or a dynamic set of hosts, you can use dynamic inventory scripts or plugins that automatically discover and list hosts.

4. **Vault for Encrypting Sensitive Data**:
   - Use Ansible Vault to encrypt sensitive data like passwords and keys in your playbooks.

   ```bash
   ansible-vault create secrets.yml
   ```

## Conclusion

With these steps, you can set up Ansible in your home lab running on Hyper-V or VirtualBox. Ansible's flexibility and ease of use make it a powerful tool for automating and managing your infrastructure. Whether you're managing a few VMs or a large-scale environment, Ansible provides a robust solution for IT automation.

If you need specific help with Hyper-V or VirtualBox configurations, feel free to ask!

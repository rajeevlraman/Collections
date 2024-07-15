---
title: Ansible_commands
description: Ansible_commands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 200
#unlisted: true
---
* 
{:toc}

### What is Ansible?

Ansible is an open-source IT automation tool used for configuration management, application deployment, orchestration, and task automation. It allows you to define infrastructure as code (IaC) and is designed to be simple yet powerful, managing nodes over SSH without requiring any agent software on the client side. Ansible's core strength lies in its simplicity and ease of use, making it an ideal choice for both small and large-scale IT operations.

### Key Features of Ansible:

- **Agentless:** Ansible operates without the need for any software agents on managed nodes.
- **Idempotent:** Ensures that repeated operations achieve the same results without side effects.
- **Declarative Language:** Uses YAML to define the desired state of the systems.
- **Extensible:** Supports custom modules and plugins for extended functionality.
- **Secure:** Uses SSH for communication and is designed to minimize security risks.

### What Can Ansible Do?

1. **Configuration Management:**
   - Ansible can manage and configure systems to ensure they maintain a desired state. For example, you can ensure that a specific version of a web server is installed and running across multiple servers.
   - **Example:** Ensuring that Apache is installed and running.
     ```yaml
     - name: Ensure Apache is installed
       yum:
         name: httpd
         state: present
     - name: Ensure Apache is running
       service:
         name: httpd
         state: started
     ```

2. **Application Deployment:**
   - Ansible simplifies application deployment, allowing you to automate the setup, deployment, and updates of applications across various environments.
   - **Example:** Deploying a web application.
     ```yaml
     - name: Deploy web application
       copy:
         src: /local/path/to/app
         dest: /var/www/html/
     ```

3. **Orchestration:**
   - Ansible can manage complex workflows by orchestrating multiple tasks across different systems. This includes managing dependencies and coordinating between services.
   - **Example:** Orchestrating a multi-tier application deployment.
     ```yaml
     - name: Deploy database
       hosts: db_servers
       tasks:
         - name: Ensure MySQL is installed
           yum:
             name: mysql-server
             state: present
         - name: Start MySQL service
           service:
             name: mysqld
             state: started

     - name: Deploy application servers
       hosts: app_servers
       tasks:
         - name: Deploy application code
           copy:
             src: /local/path/to/app
             dest: /opt/app
     ```

4. **Cloud Provisioning:**
   - Ansible can automate the provisioning and management of cloud resources across platforms like AWS, Azure, and Google Cloud.
   - **Example:** Provisioning an EC2 instance on AWS.
     ```yaml
     - name: Launch EC2 instance
       ec2:
         key_name: my_key
         instance_type: t2.micro
         image: ami-123456
         region: us-west-2
         wait: yes
     ```

5. **Security Automation:**
   - Ansible can automate security tasks such as applying patches, configuring firewalls, and managing user accounts.
   - **Example:** Applying security updates.
     ```yaml
     - name: Apply security updates
       apt:
         upgrade: dist
     ```

### Comprehensive List of Ansible Commands

Below is a comprehensive list of Ansible commands, formatted with examples and descriptions.

```markdown
# Comprehensive List of Ansible Commands

## Ansible Ad-Hoc Commands

Ad-hoc commands are used for quick, one-time tasks without writing a playbook.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible [pattern] -m ping`     | Check connectivity to the hosts                                   | `ansible all -m ping`                     |
| `ansible [pattern] -m shell -a [COMMAND]` | Execute a shell command on remote hosts                | `ansible all -m shell -a "uptime"`        |
| `ansible [pattern] -m apt -a [ARGS]` | Install a package using apt on Debian-based systems         | `ansible webservers -m apt -a "name=nginx state=present"` |
| `ansible [pattern] -m yum -a [ARGS]` | Install a package using yum on RedHat-based systems         | `ansible webservers -m yum -a "name=httpd state=present"` |
| `ansible [pattern] -m service -a [ARGS]` | Manage services on remote hosts                            | `ansible all -m service -a "name=httpd state=started"`    |
| `ansible [pattern] -m copy -a [ARGS]` | Copy files to remote hosts                                   | `ansible all -m copy -a "src=/etc/hosts dest=/tmp/hosts"` |
| `ansible [pattern] -m user -a [ARGS]` | Manage user accounts on remote hosts                        | `ansible all -m user -a "name=john state=present"`        |

## Ansible Playbook Commands

Playbooks are the core of Ansible's configuration management and orchestration. They are written in YAML and define tasks to be executed on managed hosts.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-playbook [playbook.yml]` | Run an Ansible playbook                                          | `ansible-playbook site.yml`               |
| `ansible-playbook [playbook.yml] --limit [host-pattern]` | Limit playbook execution to specific hosts            | `ansible-playbook site.yml --limit webservers` |
| `ansible-playbook [playbook.yml] --tags [tag1,tag2]` | Run only the tasks with specified tags                  | `ansible-playbook site.yml --tags "setup,deploy"` |
| `ansible-playbook [playbook.yml] --check` | Perform a dry run of the playbook                          | `ansible-playbook site.yml --check`       |
| `ansible-playbook [playbook.yml] --diff` | Show changes made by the playbook                         | `ansible-playbook site.yml --diff`        |
| `ansible-playbook [playbook.yml] --ask-become-pass` | Prompt for privilege escalation password                 | `ansible-playbook site.yml --ask-become-pass` |
| `ansible-playbook [playbook.yml] --extra-vars "[key=value]"` | Pass extra variables to the playbook              | `ansible-playbook site.yml --extra-vars "version=1.23"` |

## Ansible Inventory Commands

Ansible inventory defines the managed hosts and groups of hosts. It can be static (a file) or dynamic (a script or cloud service).

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-inventory --list`      | Display the inventory as JSON                                     | `ansible-inventory --list`                |
| `ansible-inventory --graph`     | Display inventory in a graph format                              | `ansible-inventory --graph`               |
| `ansible-inventory --host [hostname]` | Display details about a specific host                     | `ansible-inventory --host webserver1`     |
| `ansible-inventory --yaml`      | Output inventory in YAML format                                  | `ansible-inventory --yaml`                |
| `ansible-inventory --inventory [inventory_file]` | Specify the inventory file to use                | `ansible-inventory --inventory inventory.ini --list` |

## Ansible Vault Commands

Ansible Vault is used to encrypt sensitive data in your playbooks and roles.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-vault create [file]`   | Create a new encrypted file                                       | `ansible-vault create secrets.yml`        |
| `ansible-vault edit [file]`     | Edit an encrypted file                                            | `ansible-vault edit secrets.yml`          |
| `ansible-vault encrypt [file]`  | Encrypt an existing file                                          | `ansible-vault encrypt vars.yml`          |
| `ansible-vault decrypt [file]`  | Decrypt an encrypted file                                         | `ansible-vault decrypt vars.yml`          |
| `ansible-vault rekey [file]`    | Re-encrypt an existing file with a new password                   | `ansible-vault rekey secrets.yml`         |
| `ansible-playbook --ask-vault-pass [playbook.yml]` | Run a playbook with encrypted files                     | `ansible-playbook --ask-vault-pass site.yml` |

## Ansible Role Commands

Roles in Ansible are a way to organize playbooks into reusable components.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-galaxy init [role_name]` | Create a new role skeleton                                       | `ansible-galaxy init myrole`              |
| `ansible-galaxy list`           | List installed roles                                             | `ansible-galaxy list`                     |
| `ansible-galaxy install [role_name]` | Install roles from Ansible Galaxy or a tarball               | `ansible-galaxy install geerlingguy.nginx

` |
| `ansible-galaxy remove [role_name]` | Remove an installed role                                    | `ansible-galaxy remove myrole`            |
| `ansible-galaxy info [role_name]` | Show information about a role from Ansible Galaxy              | `ansible-galaxy info geerlingguy.nginx`   |

## Ansible Configuration Commands

These commands help manage Ansible configurations.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-config list`           | List all configuration options                                    | `ansible-config list`                     |
| `ansible-config dump`           | Display current configuration settings                           | `ansible-config dump`                     |
| `ansible-config view`           | View configuration file in use                                   | `ansible-config view`                     |
| `ansible-config list --disabled` | List all configuration options, including disabled options       | `ansible-config list --disabled`          |

## Ansible Collection Commands

Ansible Collections are a distribution format for Ansible content, including roles, modules, and plugins.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-galaxy collection init [collection_name]` | Create a new collection skeleton                       | `ansible-galaxy collection init mycollection` |
| `ansible-galaxy collection build` | Package the current collection                                | `ansible-galaxy collection build`         |
| `ansible-galaxy collection install [name]` | Install a collection from Ansible Galaxy                 | `ansible-galaxy collection install ansible.builtin` |
| `ansible-galaxy collection list` | List installed collections                                      | `ansible-galaxy collection list`          |
| `ansible-galaxy collection publish [path/to/tarball]` | Publish a collection to Ansible Galaxy                  | `ansible-galaxy collection publish mycollection.tar.gz` |

## Ansible Plugin Commands

Ansible plugins extend the core functionality of Ansible with custom behavior.

| **Command**                     | **Description**                                                   | **Example**                               |
|---------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `ansible-doc -t [plugin_type] [plugin_name]` | Show documentation for a plugin                           | `ansible-doc -t callback profile_tasks`   |
| `ansible-doc -l`                | List all available plugins                                       | `ansible-doc -l`                          |
| `ansible-doc --playbook-dir [dir] -t [plugin_type] [plugin_name]` | Show plugin documentation within a playbook directory   | `ansible-doc --playbook-dir ./playbooks -t connection ssh` |

This extended list of Ansible commands includes ad-hoc commands for quick operations, playbook commands for structured tasks, inventory management, Vault for encryption, roles and collections for modularity, and various configuration and plugin commands. Each command is paired with a description and an example to illustrate its usage.


This should provide a comprehensive overview of Ansible's capabilities and a detailed command list to help you manage and automate your infrastructure effectively.

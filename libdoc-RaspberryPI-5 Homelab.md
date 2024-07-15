---
title: RaspberryPI-5 Homelab
description: RaspberryPI-5 Homelab
layout: libdoc/page

#LibDoc specific below
category: Features
order: 112
#unlisted: true
---
* 
{:toc}


# Home Lab Setup on Raspberry Pi 5 Using Docker

## Prerequisites

1. **Raspberry Pi 5** with an OS installed (Raspberry Pi OS or a 64-bit version recommended).
2. **Internet Connection** for downloading Docker and containers.
3. **Basic Knowledge of Docker and Linux Command Line**.

## Step 1: Install Docker on Raspberry Pi 5

### 1.1 Update System Packages
Open a terminal and update the package list:
```bash
sudo apt update
sudo apt upgrade -y
```

### 1.2 Install Docker
Install Docker using the convenience script:
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

### 1.3 Add User to Docker Group
Allow your user to run Docker commands without `sudo`:
```bash
sudo usermod -aG docker $USER
```
**Note**: Log out and log back in for the changes to take effect.

### 1.4 Verify Docker Installation
Check if Docker is installed correctly:
```bash
docker --version
```

## Step 2: Setup Docker Containers for Home Lab

### 2.1 Install Docker Compose
Docker Compose simplifies running multi-container Docker applications:
```bash
sudo apt install -y python3-pip
sudo pip3 install docker-compose
```
Verify the installation:
```bash
docker-compose --version
```

### 2.2 Create a Project Directory
Create a directory to hold your Docker configuration files:
```bash
mkdir -p ~/homelab
cd ~/homelab
```

### 2.3 Create a `docker-compose.yml` File
This file will define the services for your Home Lab. Here’s a basic example to get you started with an ELK stack and a Kali container:

```yaml
version: '3.8'

services:
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:8.8.2
    container_name: elasticsearch
    environment:
      - discovery.type=single-node
      - "ES_JAVA_OPTS=-Xms512m -Xmx512m"
    ports:
      - "9200:9200"
    volumes:
      - esdata:/usr/share/elasticsearch/data

  logstash:
    image: docker.elastic.co/logstash/logstash:8.8.2
    container_name: logstash
    ports:
      - "5000:5000"
      - "5044:5044"
    volumes:
      - logstash-pipeline:/usr/share/logstash/pipeline
    depends_on:
      - elasticsearch

  kibana:
    image: docker.elastic.co/kibana/kibana:8.8.2
    container_name: kibana
    ports:
      - "5601:5601"
    depends_on:
      - elasticsearch

  kali:
    image: kalilinux/kali-rolling
    container_name: kali
    tty: true
    networks:
      - homelab

volumes:
  esdata:
  logstash-pipeline:

networks:
  homelab:
```

### 2.4 Deploy the Containers
Navigate to the directory containing your `docker-compose.yml` file and deploy the stack:
```bash
docker-compose up -d
```

## Step 3: Access and Configure Your Services

### 3.1 Access Elasticsearch
Open your web browser and navigate to `http://<RaspberryPi_IP>:9200` to check if Elasticsearch is running.

### 3.2 Access Kibana
Navigate to `http://<RaspberryPi_IP>:5601` to access the Kibana dashboard.

### 3.3 Access Kali Container
Attach to the Kali container to start using it:
```bash
docker exec -it kali /bin/bash
```

### 3.4 Configure Logstash
You’ll need to create configuration files for Logstash to process logs. These should be placed in the `logstash-pipeline` volume specified in the `docker-compose.yml`.

Example Logstash configuration (`~/homelab/logstash-pipeline/logstash.conf`):
```plaintext
input {
  beats {
    port => 5044
  }
}

filter {
  # Add filters here
}

output {
  elasticsearch {
    hosts => ["http://elasticsearch:9200"]
  }
  stdout { codec => rubydebug }
}
```

Restart the Logstash container to apply the configuration:
```bash
docker restart logstash
```

## Step 4: Simulate Attacks from Kali

From the Kali container, you can start various security assessments and attacks against your setup to simulate a SOC environment. Tools like `nmap`, `metasploit`, and others are pre-installed in Kali Linux.

### Example: Basic Nmap Scan
```bash
nmap -A <Target_IP>
```

## Step 5: Monitor and Analyze Logs in Kibana

Use the Kibana interface to visualize and analyze the data coming into your ELK stack from various sources.

## Conclusion

You now have a basic Home Lab setup on your Raspberry Pi 5 using Docker. This environment can be expanded with more containers and configurations as needed. Happy testing!



This Markdown guide provides a comprehensive overview of setting up a home lab using a Raspberry Pi 5 with Docker, focusing on SIEM and SOC analyst tools and simulations. Adjust the configurations and add more services as per your specific requirements.

<!-- doker best practices -->

When setting up Docker on a Raspberry Pi, following best practices ensures a clean, organized, and maintainable environment. Here’s a detailed guide on the best practices for installing Docker and organizing your setup:

## Best Practices for Installing Docker on Raspberry Pi

### 1. System Preparation

1. **Start with a Fresh Install**: Begin with a clean installation of the Raspberry Pi OS (preferably the 64-bit version for better performance and compatibility).

2. **Regular Updates**: Keep your system up-to-date to ensure security and stability.
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

3. **Basic Tools Installation**: Install essential tools and utilities.
   ```bash
   sudo apt install -y curl git vim
   ```

### 2. Directory Organization

Organize your files and directories to separate system files, Docker binaries, configuration files, and project-specific data.

1. **Create a Dedicated Directory for Docker Projects**
   ```bash
   mkdir -p ~/docker-projects
   ```

2. **Set up Specific Directories for Configurations and Data**
   - Keep Docker and Docker Compose configuration files in a dedicated directory.
   - Store persistent data volumes and project-specific configurations in structured subdirectories.

### 3. Install Docker

1. **Use Official Docker Script**: Install Docker using the official convenience script from Docker. This method ensures you get the latest stable release and proper installation.
   ```bash
   curl -fsSL https://get.docker.com -o ~/docker-projects/get-docker.sh
   sudo sh ~/docker-projects/get-docker.sh
   ```

2. **Enable Docker to Start on Boot**
   ```bash
   sudo systemctl enable docker
   sudo systemctl start docker
   ```

3. **Add User to Docker Group**: This allows running Docker commands without `sudo`.
   ```bash
   sudo usermod -aG docker $USER
   ```

   **Note**: Log out and log back in to apply the group changes.

4. **Verify Docker Installation**
   ```bash
   docker --version
   ```

### 4. Install Docker Compose

1. **Install Docker Compose**: Using `pip3` is a common method for installing Docker Compose on Raspberry Pi.
   ```bash
   sudo apt install -y python3-pip
   sudo pip3 install docker-compose
   ```

2. **Verify Docker Compose Installation**
   ```bash
   docker-compose --version
   ```

### 5. Organize Docker Projects

1. **Create a Separate Directory for Each Project**
   - Keep each project in its own directory under `~/docker-projects/` for better organization and isolation.
   ```bash
   mkdir -p ~/docker-projects/project-name
   cd ~/docker-projects/project-name
   ```

2. **Use `docker-compose.yml` for Multi-Container Applications**
   - Define your Docker services in `docker-compose.yml` within the project directory.
   - Store project-specific configurations and scripts in the project directory.

### 6. Configuration Management

1. **Store Configuration Files in a Consistent Location**
   - Create a directory for configurations within each project directory.
   ```bash
   mkdir -p ~/docker-projects/project-name/config
   ```

2. **Use Environment Files for Configurations**
   - Store environment-specific variables in `.env` files within your project directories.
   ```bash
   touch ~/docker-projects/project-name/.env
   ```

3. **Volume Management**
   - Use Docker volumes to persist data. Keep volume declarations in the `docker-compose.yml` and mount them to specific directories.
   - Create a `volumes` directory within each project to manage these data volumes.
   ```bash
   mkdir -p ~/docker-projects/project-name/volumes
   ```

### 7. Security Best Practices

1. **Limit Permissions**: Run Docker services with the least privileges necessary.
   
2. **Keep Docker Updated**: Regularly update Docker and Docker Compose to the latest versions.
   ```bash
   sudo apt update && sudo apt upgrade docker-ce docker-ce-cli containerd.io
   ```

3. **Use Secure Images**: Pull images from trusted sources and check for vulnerabilities.
   ```bash
   docker scan <image_name>
   ```

4. **Network Security**: Use Docker networks to isolate services and secure inter-container communication.
   ```yaml
   networks:
     frontend:
     backend:
   ```

### 8. Backup and Recovery

1. **Backup Docker Configurations and Data**:
   - Regularly back up your `docker-compose.yml`, `.env` files, and data volumes.

2. **Automate Backups**: Use cron jobs or backup tools to automate the backup process.

### 9. Monitoring and Logging

1. **Set Up Monitoring Tools**:
   - Use tools like Prometheus, Grafana, or ELK stack to monitor Docker services and performance.

2. **Centralized Logging**: Collect and analyze logs from Docker containers centrally using ELK or Fluentd.

### 10. Cleanup and Maintenance

1. **Remove Unused Resources**: Periodically clean up unused Docker images, containers, and volumes.
   ```bash
   docker system prune -a
   ```

2. **Monitor Disk Usage**:
   - Keep track of disk usage and ensure you have enough space for Docker operations.
   ```bash
   df -h
   ```

By following these best practices, you can set up a professional, streamlined, and maintainable Docker environment on your Raspberry Pi.

### Summary

Below is the summarized directory structure for reference:

```plaintext
/home/pi/
└── docker-projects/
    ├── get-docker.sh        # Docker installation script
    ├── project-name/        # Example project directory
    │   ├── docker-compose.yml
    │   ├── .env
    │   ├── config/          # Configuration files
    │   └── volumes/         # Persistent data volumes
    └── another-project/     # Another project directory
        ├── docker-compose.yml
        ├── .env
        ├── config/
        └── volumes/
```

This structure helps maintain a clean and organized environment for Docker development and deployment on Raspberry Pi.

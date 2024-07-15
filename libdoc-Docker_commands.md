---
title: Docker_commands
description: Docker_commands
layout: libdoc/page

#LibDoc specific below
category: Commands
order: 202
#unlisted: true
---
* 
{:toc}


# Comprehensive List of Docker Commands

## Docker Container Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]` | Run a new container from a specified image           | `docker run -d -p 80:80 nginx`            |
| `docker ps`                       | List all running containers                                       | `docker ps`                               |
| `docker ps -a`                    | List all containers (running and stopped)                         | `docker ps -a`                            |
| `docker stop [CONTAINER]`         | Stop a running container                                          | `docker stop my-container`                |
| `docker start [CONTAINER]`        | Start a stopped container                                         | `docker start my-container`               |
| `docker restart [CONTAINER]`      | Restart a container                                               | `docker restart my-container`             |
| `docker rm [CONTAINER]`           | Remove a stopped container                                        | `docker rm my-container`                  |
| `docker logs [CONTAINER]`         | Fetch the logs of a container                                     | `docker logs my-container`                |
| `docker exec [OPTIONS] CONTAINER COMMAND [ARG...]` | Run a command inside a running container             | `docker exec -it my-container /bin/bash`  |
| `docker attach [CONTAINER]`       | Attach to a running container’s console                           | `docker attach my-container`              |
| `docker inspect [CONTAINER]`      | Display detailed information on a container                       | `docker inspect my-container`             |
| `docker top [CONTAINER]`          | Display the running processes of a container                      | `docker top my-container`                 |
| `docker cp [CONTAINER:SRC_PATH] DEST_PATH` | Copy files from a container to the host                 | `docker cp my-container:/path/to/file /host/path` |
| `docker pause [CONTAINER]`        | Pause all processes in a container                                | `docker pause my-container`               |
| `docker unpause [CONTAINER]`      | Unpause all processes in a container                              | `docker unpause my-container`             |
| `docker rename [CONTAINER] NEW_NAME` | Rename a container                                          | `docker rename my-container new-name`     |
| `docker stats [CONTAINER]`        | Display a live stream of resource usage statistics for a container | `docker stats my-container`               |
| `docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]` | Create a new image from a container’s changes       | `docker commit my-container my-new-image` |
| `docker diff [CONTAINER]`         | Inspect changes to files or directories on a container’s filesystem | `docker diff my-container`                |

## Docker Image Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker pull [OPTIONS] NAME[:TAG@DIGEST]` | Download an image from a registry                          | `docker pull ubuntu:latest`               |
| `docker images`                   | List all images on the local system                                | `docker images`                           |
| `docker rmi [OPTIONS] IMAGE [IMAGE...]` | Remove one or more images                                   | `docker rmi ubuntu:latest`                |
| `docker build [OPTIONS] PATH  URL` | Build an image from a Dockerfile                            | `docker build -t my-image .`              |
| `docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]` | Tag an image into a repository                        | `docker tag ubuntu:latest my-ubuntu:1.0`  |
| `docker save [OPTIONS] IMAGE [IMAGE...]` | Save one or more images to a tar archive                  | `docker save -o ubuntu.tar ubuntu:latest` |
| `docker load [OPTIONS]`           | Load an image from a tar archive or STDIN                        | `docker load -i ubuntu.tar`               |
| `docker history [OPTIONS] IMAGE`  | Show the history of an image                                      | `docker history ubuntu:latest`            |
| `docker inspect [OPTIONS] IMAGE [IMAGE...]` | Display detailed information on one or more images     | `docker inspect ubuntu:latest`            |

## Docker Volume Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker volume create [OPTIONS] [VOLUME]` | Create a new volume                                     | `docker volume create my-volume`          |
| `docker volume ls`                | List all volumes on the system                                    | `docker volume ls`                        |
| `docker volume rm [VOLUME]`       | Remove a specified volume                                        | `docker volume rm my-volume`              |
| `docker volume inspect [VOLUME]`  | Display detailed information on a volume                         | `docker volume inspect my-volume`         |
| `docker volume prune`             | Remove all unused volumes                                        | `docker volume prune`                     |

## Docker Network Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker network create [OPTIONS] NETWORK` | Create a new network                                   | `docker network create my-network`        |
| `docker network ls`               | List all networks on the system                                    | `docker network ls`                       |
| `docker network rm [NETWORK]`     | Remove a specified network                                        | `docker network rm my-network`            |
| `docker network inspect [NETWORK]`| Display detailed information on a network                         | `docker network inspect my-network`       |
| `docker network connect [OPTIONS] NETWORK CONTAINER` | Connect a container to a network                     | `docker network connect my-network my-container` |
| `docker network disconnect [OPTIONS] NETWORK CONTAINER` | Disconnect a container from a network             | `docker network disconnect my-network my-container` |

## Docker Compose Commands

Docker Compose simplifies multi-container application deployments.

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker-compose up [OPTIONS] [SERVICE...]` | Create and start containers                           | `docker-compose up -d`                    |
| `docker-compose down [OPTIONS]`   | Stop and remove containers, networks, images, and volumes       | `docker-compose down`                     |
| `docker-compose start [SERVICE...]` | Start existing containers                                | `docker-compose start`                    |
| `docker-compose stop [SERVICE...]` | Stop running containers                                   | `docker-compose stop`                     |
| `docker-compose restart [SERVICE...]` | Restart containers                                     | `docker-compose restart`                  |
| `docker-compose build [OPTIONS] [SERVICE...]` | Build or rebuild services                           | `docker-compose build`                    |
| `docker-compose ps`               | List containers                                              | `docker-compose ps`                       |
| `docker-compose logs [OPTIONS] [SERVICE...]` | View output from containers                       | `docker-compose logs`                     |
| `docker-compose exec [OPTIONS] SERVICE COMMAND [ARGS...]` | Execute a command in a running container | `docker-compose exec web /bin/bash`       |
| `docker-compose pull [OPTIONS] [SERVICE...]` | Pull service images                                 | `docker-compose pull`                     |

## Docker Swarm Commands

Docker Swarm provides native clustering and orchestration for Docker containers.

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker swarm init [OPTIONS]`     | Initialize a swarm                                                | `docker swarm init --advertise-addr 192.168.1.100` |
| `docker swarm join [OPTIONS]`     | Join a node to a swarm                                            | `docker swarm join --token SWMTKN-1-4 192.168.1.100:2377` |
| `docker node ls`                  | List all nodes in the swarm                                       | `docker node ls`                          |
| `docker service create [OPTIONS] IMAGE [COMMAND] [ARG...]` | Create a new service                                  | `docker service create --name my-service -p 80:80 nginx` |
| `docker service ls`               | List all services in the swarm                                    | `docker service ls`                       |
| `docker service ps [SERVICE]`     | List the tasks of a service                                       | `docker service ps my-service`            |
| `docker service scale [SERVICE=REPLICAS...]` | Scale one or multiple services                   | `docker service scale my-service=3`       |
| `docker stack deploy [OPTIONS] STACK` | Deploy a new stack or update an existing stack     | `docker stack deploy -c docker-compose.yml my-stack` |
| `docker stack ls`                 | List stacks                                                      | `docker stack ls`                         |
| `docker stack ps [OPTIONS] STACK` | List the tasks in a stack                                         | `docker stack ps my-stack`                |
| `docker stack rm [STACK...]`      | Remove one or more stacks                                         | `docker stack rm my-stack`                |

## Docker Security and Configuration Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker login [OPTIONS] [SERVER]` | Log in to a Docker registry                                        | `docker login`                            |
| `docker logout [SERVER]`          | Log out from a Docker registry                                     | `docker logout`                           |
| `docker system df`                | Show docker disk usage                                             | `docker system df`                        |
| `docker system prune [OPTIONS]`   | Remove unused data (containers, networks, images, and volumes)    | `docker system prune -f`                  |
| `docker update [OPTIONS] CONTAINER [CONTAINER...]` | Update configuration of one or more containers | `docker update --restart=always my-container` |
| `docker stats [OPTIONS] [CONTAINER...]` | Display a live stream of container(s) resource usage statistics | `docker stats my-container`               |
| `docker info`                     | Display system-wide information                                    | `docker info`                             |
| `docker version`                  | Show the Docker version information                                | `docker version`                          |

## Docker Network Management

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker network create [OPTIONS] NETWORK` | Create a new network                                      | `docker network create my-network`        |
| `docker network ls`               | List networks                                                   | `docker network ls`                       |
| `docker network inspect NETWORK`  | Display detailed information on a network                        | `docker network inspect my-network`       |
| `docker network rm NETWORK`       | Remove one or more networks                                       | `docker network rm my-network`            |
| `docker network connect NETWORK CONTAINER` | Connect a container to a network                   | `docker network connect my-network my-container` |
| `docker network disconnect NETWORK CONTAINER` | Disconnect a container from a network             | `docker network disconnect my-network my-container` |

## Docker Volume Management

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker volume create [OPTIONS] [VOLUME]` | Create a new volume                                          | `docker volume create my-volume`          |
| `docker volume ls`                | List volumes                                                    | `docker volume ls`                        |
| `docker volume inspect VOLUME`    | Display detailed information on a volume                         | `docker volume inspect my-volume`         |
| `docker volume rm VOLUME`         | Remove one or more volumes                                        | `docker volume rm my-volume`              |
| `docker volume prune [OPTIONS]`   | Remove all unused local volumes                                   | `docker volume prune`                     |

## Docker System Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker system info`              | Display system-wide information                                   | `docker system info`                      |
| `docker system df`                | Show docker disk usage                                             | `docker system df`                        |
| `docker system prune [OPTIONS]`   | Remove unused data (containers, networks, images, and volumes)    | `docker system prune -f`                  |
| `docker system events [OPTIONS]`  | Get real-time events from the server                               | `docker system events`                    |

This extensive list covers a broad range of Docker commands used for managing containers, images, volumes, networks, Docker Compose, Docker Swarm, security, configuration, and system operations. Each command includes a description and an example to demonstrate its usage.


***This list includes additional Docker commands and more specific use cases that go beyond the standard ones. This would include some advanced commands, configuration settings, and troubleshooting techniques. Here are a few more commands and examples:***

# Additional Docker Commands

## Advanced Docker Container Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker run --rm [OPTIONS] IMAGE [COMMAND] [ARG...]` | Run a container and automatically remove it when it exits | `docker run --rm ubuntu echo "Hello, World!"` |
| `docker run --name [NAME] [OPTIONS] IMAGE [COMMAND] [ARG...]` | Run a container with a specific name                   | `docker run --name my-container -d nginx` |
| `docker run --network [NETWORK] [OPTIONS] IMAGE [COMMAND] [ARG...]` | Attach a container to a specific network               | `docker run --network my-network -d nginx` |
| `docker update [OPTIONS] CONTAINER` | Update configuration of one or more containers               | `docker update --memory 512m my-container` |
| `docker rename CONTAINER NEW_NAME` | Rename an existing container                                | `docker rename old-name new-name`         |
| `docker wait [CONTAINER]`         | Block until a container stops, then print the exit code         | `docker wait my-container`                |
| `docker port [CONTAINER]`         | List port mappings for the container                            | `docker port my-container`                |
| `docker export [OPTIONS] CONTAINER` | Export a container’s filesystem as a tar archive             | `docker export -o my-container.tar my-container` |
| `docker import [OPTIONS] fileURL- [REPOSITORY[:TAG]]` | Import the contents from a tarball to create a filesystem image | `docker import my-container.tar` |
| `docker checkpoint create [OPTIONS] CONTAINER CHECKPOINT` | Create a checkpoint from a running container         | `docker checkpoint create my-container checkpoint1` |
| `docker checkpoint ls [OPTIONS] CONTAINER` | List checkpoints for a container                         | `docker checkpoint ls my-container`       |
| `docker checkpoint rm [OPTIONS] CONTAINER CHECKPOINT` | Remove a checkpoint from a container                   | `docker checkpoint rm my-container checkpoint1` |

## Advanced Docker Image Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker push [OPTIONS] NAME[:TAG]`| Push an image or a repository to a registry                        | `docker push my-image:latest`             |
| `docker image prune [OPTIONS]`    | Remove unused images                                              | `docker image prune -a`                   |
| `docker tag [SOURCE_IMAGE] [TARGET_IMAGE]` | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE | `docker tag my-image:latest my-repo/my-image:1.0` |
| `docker image inspect [OPTIONS] IMAGE [IMAGE...]` | Display detailed information on one or more images    | `docker image inspect ubuntu:latest`      |
| `docker image ls`                 | List images                                                       | `docker image ls`                         |

## Advanced Docker Volume Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker volume ls -q`             | List volume names only                                            | `docker volume ls -q`                     |
| `docker volume rm $(docker volume ls -qf dangling=true)` | Remove all dangling volumes                             | `docker volume rm $(docker volume ls -qf dangling=true)` |

## Advanced Docker Network Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker network prune`            | Remove all unused networks                                        | `docker network prune`                   |
| `docker network create --driver bridge overlay NETWORK` | Create a network with a specified driver            | `docker network create --driver bridge my-bridge-network` |
| `docker network create --subnet 192.168.1.0/24 NETWORK` | Create a network with a specified subnet               | `docker network create --subnet 192.168.1.0/24 my-subnet-network` |
| `docker network inspect -f {{json .Containers}} NETWORK` | Display detailed information about containers connected to a network | `docker network inspect -f '{{json .Containers}}' my-network` |

## Docker Configuration and Resource Management Commands

| **Command**                                    | **Description**                                                  | **Example**                                |
|------------------------------------------------|------------------------------------------------------------------|--------------------------------------------|
| `docker system df --verbose`                   | Show detailed disk usage information                             | `docker system df --verbose`               |
| `docker system prune --volumes`                | Remove all unused data including volumes                         | `docker system prune --volumes`            |
| `docker update --cpus [CPU_SHARES] CONTAINER` | Change container CPU limit                                        | `docker update --cpus 2 my-container`      |
| `docker update --memory [MEMORY_LIMIT] CONTAINER` | Change container memory limit                                 | `docker update --memory 512m my-container` |
| `docker system events --filter event=start`    | Stream real-time events with filters                             | `docker system events --filter event=start`|


## Docker Troubleshooting Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker events [OPTIONS]`         | Get real-time events from the Docker server                       | `docker events`                          |
| `docker inspect --format {{.State.Status}} CONTAINER` | Get the status of a container   |           `docker inspect --format {{.State.Status}} my-container` |
| `docker logs --details [CONTAINER]` | Get detailed logs from a container                          | `docker logs --details my-container`      |
| `docker logs --since TIME [CONTAINER]` | Show logs since a specific timestamp                      | `docker logs --since 1h my-container`     |
| `docker logs --tail [LINES] [CONTAINER]` | Show only the last few lines of logs                     | `docker logs --tail 100 my-container`     |
| `docker logs --follow [CONTAINER]` | Follow the log output from a container                        | `docker logs --follow my-container`       |

## Docker Tagging and Metadata Management

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker tag [OPTIONS] SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]` | Add a tag to a specified image                      | `docker tag ubuntu:latest myrepo/ubuntu:latest` |
| `docker inspect --format '{{json .RepoTags}}' IMAGE` | Get tags for a specific image                       | `docker inspect --format '{{json .RepoTags}}' ubuntu:latest` |

## Docker Security Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker scan [OPTIONS] IMAGE`     | Scan an image for vulnerabilities                                | `docker scan ubuntu:latest`               |
| `docker trust inspect [OPTIONS] IMAGE` | Show trust status of an image                           | `docker trust inspect ubuntu:latest`      |
| `docker trust sign [OPTIONS] IMAGE` | Sign an image for trusted content                           | `docker trust sign ubuntu:latest`         |
| `docker trust revoke [OPTIONS] IMAGE` | Revoke an image’s trust status                             | `docker trust revoke ubuntu:latest`       |

## Docker Build and Automation Commands

| **Command**                       | **Description**                                                   | **Example**                               |
|-----------------------------------|-------------------------------------------------------------------|-------------------------------------------|
| `docker build --no-cache [OPTIONS] PATH` | Build an image without using the cache                    | `docker build --no-cache -t my-image .`   |
| `docker build --pull [OPTIONS] PATH` | Always attempt to pull a newer version of the base image during build | `docker build --pull -t my-image .`       |
| `docker build --build-arg [KEY=VALUE] PATH` | Set build-time variables                              | `docker build --build-arg USERNAME=user .` |
| `docker buildx create [OPTIONS] CONTEXT` | Create a new build instance with extended capabilities | `docker buildx create --use --name mybuilder` |

This extended list includes more advanced Docker commands and use cases, covering a wide range of functionalities from advanced container and image management to Docker security and troubleshooting. Each command is paired with a description and an example to provide clear guidance on its usage.

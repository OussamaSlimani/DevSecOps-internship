# Docker

---

## 1. **What is Docker**

Docker is a tool designed to simplify the creation, deployment, and execution of applications using containers. Containers allow developers to package an application with all its dependencies and run it in isolation from the rest of the system.

## 2. **Key Concepts**

- **Image:** A Docker image is a read-only template used to create containers. It contains everything needed to run an application: code, runtime, libraries, environment variables, and more.
- **Container:** A container is a running instance of an image. It is lightweight and portable, running in isolation.
  Dockerfile: A text file that contains instructions for building a Docker image.
- **Registry:** A repository for storing and distributing Docker images. Docker Hub is a popular example of a public registry.
- **Docker Engine:** The core component of Docker, Docker Engine is a client-server application that includes a server (a long-running daemon process), a REST API for interacting with the daemon, and a command-line interface (CLI) client.

## 3. **Docker Image**

### 3.1 **Build an image from a Dockerfile:**

```bash
docker build -t image_name path_to_dockerfile
```

### 3.2 **List all local images:**

```bash
docker images
```

### 3.3 **Pull an image from Docker Hub:**

```bash
docker pull image_name:tag
```

### 3.4 **Remove a local image:**

```bash
docker rmi image_name:tag
```

### 3.5 **Tag an image:**

```bash
docker tag source_image:tag new_image:tag
```

### 3.6 **Push an image to Docker Hub:**

```bash
docker push image_name:tag
```

### 3.7 **Inspect details of an image:**

```bash
docker image inspect image_name:tag
```

### 3.8 **Save an image to a tar archive:**

```bash
docker save -o image_name.tar image_name:tag
```

### 3.9 **Load an image from a tar archive:**

```bash
docker load -i image_name.tar
```

### 3.10 **Prune unused images:**

```bash
docker image prune
```

## 4. **Docker Container**

### 4.1 **Run a new container from an image:**

```bash
docker run container_name image_name
```

### 4.2 **Run a named container from an image:**

```bash
docker run --name container_name image_name:tag
```

### 4.3 **List all running containers:**

```bash
docker ps
```

### 4.4 **List all containers (including stopped ones):**

```bash
docker ps -a
```

### 4.5 **Stop a running container:**

```bash
docker stop container_name_or_id
```

### 4.6 **Restart a stopped container:**

```bash
docker start container_name_or_id
```

### 4.7 **Run container in interactive mode:**

```bash
docker run -it container_name_or_id
```

### 4.8 **Run container in interactive shell mode:**

```bash
docker run -it container_name_or_id sh
```

### 4.9 **Remove a stopped container:**

```bash
docker rm container_name_or_id
```

### 4.10 **Remove a running container (forcefully):**

```bash
docker rm -f container_name_or_id
```

### 4.11 **Inspect details of a container:**

```bash
docker inspect container_name_or_id
```

### 4.12 **View container logs:**

```bash
docker logs container_name_or_id
```

### 4.13 **Pause a running container:**

```bash
docker pause container_name_or_id
```

### 4.14 **Unpause a paused container:**

```bash
docker unpause container_name_or_id
```

## 5. **Docker Compose**

### 5.1 **Create and start containers defined in a docker-compose.yml file:**

This command reads the docker-compose.yml file and starts the defined services in the background.

```bash
docker compose up
```

### 5.2 **Stop and remove containers defined in a docker-compose.yml file:**

This command stops & removes the containers, networks, and volumes defined in the docker-compose.yml file.

```bash
docker compose down
```

### 5.3 **Build or rebuild services:**

This command builds or rebuilds the Docker images for the services defined in the docker-compose.yml file.

```bash
docker compose build
```

### 5.4 **List containers for a specific Docker Compose project:**

This command lists the containers for the services defined in the docker-compose.yml file.

```bash
docker compose ps
```

### 5.5 **View logs for services:**

This command displays the logs for the services defined in the docker-compose.yml file.

```bash
docker compose logs
```

### 5.6 **Scale services to a specific number of containers:**

This command scales the services defined in the docker-compose.yml file to the specified number of containers.

```bash
docker compose up -d --scale service_name=number_of_containers
```

### 5.7 **Run a one-time command in a service:**

```bash
docker compose run service_name command
```

### 5.8 **List all volumes:**

Docker Compose creates volumes for services. This command helps you see them.

```bash
docker volume ls
```

### 5.9 **Pause a service:**

This command pauses the specified service.

```bash
docker pause service_name
```

### 5.10 **Unpause a service:**

This command unpauses the specified service.

```bash
docker unpause service_name
```

### 5.11 **View details of a service:**

Provides detailed information about a specific service.

```bash
docker compose ps service_name
```

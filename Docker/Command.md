
# Docker Basic Commands – Learning Reference

---

```bash
# Check Docker installation and version
docker --version
docker info

# List all Docker images
docker images

# List all running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Pull images from Docker Hub
docker pull ubuntu:latest
docker pull nginx:latest
docker pull mongo:latest

# Run containers
docker run -it ubuntu /bin/bash
docker run -d -p 8080:80 --name webserver nginx
docker run -d -p 27017:27017 --name mongodb mongo
docker run -d -p 5000:5000 -v $(pwd):/app --name myapp myimage:latest

# Manage containers
docker stop <container_name_or_id>
docker start <container_name_or_id>
docker restart <container_name_or_id>
docker rm <container_name_or_id>

# Manage images
docker rmi <image_name_or_id>
docker build -t myimage:latest .
docker tag myimage:latest myrepo/myimage:v1
docker login
docker push myrepo/myimage:v1


# Clean up unused data
docker system prune -a

# View container logs
docker logs <container_name_or_id>

# Access a running container shell
docker exec -it <container_name_or_id> /bin/bash

# Copy files between host and container
docker cp ./myfile.txt <container_name>:/usr/src/app/
docker cp <container_name>:/usr/src/app/output.txt .

# Save and load images
docker save -o myimage.tar myimage:latest
docker load -i myimage.tar

# Inspect detailed info about a container
docker inspect <container_name_or_id>

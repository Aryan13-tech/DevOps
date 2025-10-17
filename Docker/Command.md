# -----------------------------------------
# Docker Basic Commands – Learning Reference
# -----------------------------------------

# 🧩 1. Check Docker installation & version
docker --version
docker info

# 🧩 2. List all Docker images
docker images

# 🧩 3. List all running containers
docker ps

# 🧩 4. List all containers (including stopped ones)
docker ps -a

# 🧩 5. Pull an image from Docker Hub
docker pull ubuntu:latest
docker pull nginx:latest
docker pull mongo:latest

# 🧩 6. Run a container (interactive mode)
docker run -it ubuntu /bin/bash

# 🧩 7. Run NGINX container (detached mode, port mapping)
docker run -d -p 8080:80 --name webserver nginx

# 🧩 8. Run MongoDB container
docker run -d -p 27017:27017 --name mongodb mongo

# 🧩 9. Run custom image with mounted volume
docker run -d -p 5000:5000 -v $(pwd):/app --name myapp myimage:latest

# 🧩 10. Stop a running container
docker stop <container_name_or_id>

# 🧩 11. Start a stopped container
docker start <container_name_or_id>

# 🧩 12. Restart a container
docker restart <container_name_or_id>

# 🧩 13. Remove a stopped container
docker rm <container_name_or_id>

# 🧩 14. Remove an image
docker rmi <image_name_or_id>

# 🧩 15. Remove all stopped containers and unused data
docker system prune -a

# 🧩 16. Show container logs
docker logs <container_name_or_id>

# 🧩 17. Access a running container shell
docker exec -it <container_name_or_id> /bin/bash

# 🧩 18. Copy files from host to container
docker cp ./myfile.txt <container_name>:/usr/src/app/

# 🧩 19. Copy files from container to host
docker cp <container_name>:/usr/src/app/output.txt .

# 🧩 20. Build a Docker image from Dockerfile
docker build -t myimage:latest .

# 🧩 21. Tag an image
docker tag myimage:latest myrepo/myimage:v1

# 🧩 22. Push image to Docker Hub
docker login
docker push myrepo/myimage:v1

# 🧩 23. Save an image to tar file
docker save -o myimage.tar myimage:latest

# 🧩 24. Load image from tar file
docker load -i myimage.tar

# 🧩 25. View detailed info about container
docker inspect <container_name_or_id>

# -----------------------------------------
# End of Docker Command Reference
# -----------------------------------------


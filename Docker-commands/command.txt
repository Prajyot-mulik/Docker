
# Docker Cheat Sheet: Basic to Advanced Commands

## Docker Basic Commands

# 1. Verify Docker installation
docker --version

# 2. Pull an image from Docker Hub
docker pull <image-name>:<tag>
# Example:
docker pull nginx:latest

# 3. List all Docker images on the system
docker images

# 4. Run a container in detached mode (-d) and expose it to the host
docker run -d --name <container-name> -p <host-port>:<container-port> <image-name>:<tag>
# Example:
docker run -d --name my-nginx -p 8080:80 nginx:latest

# 5. List all running containers
docker ps

# 6. List all containers (both running and stopped)
docker ps -a

# 7. Stop a running container
docker stop <container-name>

# 8. Start a stopped container
docker start <container-name>

# 9. Remove a container
docker rm <container-name>

# 10. Remove a Docker image
docker rmi <image-name>:<tag>

# 11. View logs of a running container
docker logs <container-name>

# 12. Execute a command in a running container
docker exec -it <container-name> <command>
# Example:
docker exec -it my-nginx /bin/bash

## Docker Intermediate Commands

# 13. Build an image from a Dockerfile
docker build -t <image-name>:<tag> <path-to-dockerfile>
# Example:
docker build -t my-app:latest .

# 14. Push an image to Docker Hub
docker push <username>/<image-name>:<tag>
# Example:
docker push myusername/my-app:latest

# 15. Tag an image for a repository
docker tag <image-id> <username>/<repository-name>:<tag>
# Example:
docker tag abc123 myusername/my-app:latest

# 16. Run a container interactively
docker run -it <image-name>:<tag> /bin/bash

# 17. View container resource usage
docker stats

## Docker Advanced Commands

# 18. Docker Compose: Start services from a docker-compose.yml file
docker-compose up

# 19. Docker Compose: Stop and remove all containers
docker-compose down

# 20. Export and save a Docker image to a file
docker save -o <output-file.tar> <image-name>:<tag>
# Example:
docker save -o my-app.tar my-app:latest

# 21. Import a Docker image from a file
docker load -i <input-file.tar>
# Example:
docker load -i my-app.tar

# 22. Clean up unused containers, networks, and images
docker system prune -a

# 23. View Docker networks
docker network ls

# 24. Create a custom Docker network
docker network create <network-name>

# 25. Connect a container to a custom network
docker network connect <network-name> <container-name>

# 26. Disconnect a container from a custom network
docker network disconnect <network-name> <container-name>

## Git Commands to Push Docker Project to GitHub

# 27. Initialize a new Git repository
git init

# 28. Add all files to the repository
git add .

# 29. Commit the files
git commit -m "Initial Docker project commit"

# 30. Add a remote GitHub repository (replace the URL with your repository URL)
git remote add origin https://github.com/<your-username>/<repository-name>.git

# 31. Push the code to GitHub
git push -u origin master


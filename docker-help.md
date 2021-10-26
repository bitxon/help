# Docker

## Image
Base commands
```bash
# List all images
docker image ls
# Build and tag image
docker build -t myimage:latest .
# Remove image
docker image rm myimage:latest
# Save image backup
docker save -o myimage.tar myimage:latest
# Load image from backupfile
docker load -i myimage.tar
```

## Container
Base commands
```bash
# List all containers
docker ps
# Run container from image
docker run --name <name> -p 27017:27017 node
# Run container interactive
docker run -it --rm busybox
# Stop container by container id
docker stop <container-id>
# Re-start container by container id
docker start <container-id>
# Show the last 100 lines of logs
docker container logs --tail 100 <container-id>
```
Adjustment commands
```bash
# Copy File to local machine
docker cp <container-id>:/tmp/myfile.txt myfile.txt 
# Copy File to container
docker cp <container-id>:/tmp/myfile.txt myfile.txt 
```

## Compose
Base commands
```bash
# Up with build
docker-compose -f "docker-compose.yml" up -d --build
```

## Advanced docker commands

### Dangling images
```bash
# List all dangling images
docker images --filter "dangling=true" -q --no-trunc
# Remove all dangling images
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
```

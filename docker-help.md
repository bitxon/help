# Docker

## Image
```bash
# List all images
docker image ls

# Build and tag image
docker build -t myimage:latest .

# Remove image
docker image rm myimage:latest
```

## Container
```bash
# List all containers
docker ps

# Run container from image
docker run --name <name> -p 27017:27017 node

# Stop container by container id
docker stop <container-id>

# Re-start container by container id
docker start <container-id>

# Show the last 100 lines of logs
docker container logs --tail 100 <container-id>
```

## Advanced docker commands

### Dangling images
```bash
# List all dangling images
docker images --filter "dangling=true" -q --no-trunc
# Remove all dangling images
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
```

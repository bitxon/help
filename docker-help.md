# Docker

## Base docker commands
```bash
# Build and tag image
docker build -t <image-tag> .

# Run container from image
docker run -p 27017:27017 node

# Stop container by container id
docker stop <container-id>

# Re-start container by container id
docker start <container-id>

# List containers
docker ps
```

## Advanced docker commands

### Show all dangling images
```bash
docker images --filter "dangling=true" -q --no-trunc
```

### Remove All danling images
```bash
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
```

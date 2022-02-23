### Create the image

```
docker buildx build --platform linux/arm64 -t prnewsio/redis:latest.arm --force-rm --no-cache .
docker login -u="\$DOCKER_USERNAME" -p="\$DOCKER_PASSWORD"
docker push prnewsio/redis:latest.arm
```

### Run with docker-compose

```
...
    image: prnewsio/redis:latest
    command:
      - redis-server
      - /var/local/conf/maxmemory-1G.conf
...      
```
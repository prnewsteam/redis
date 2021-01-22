### Create the image

```
docker build -t prnewsio/redis:latest --force-rm --no-cache .
docker login -u="\$DOCKER_USERNAME" -p="\$DOCKER_PASSWORD"
docker push prnewsio/redis:latest
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
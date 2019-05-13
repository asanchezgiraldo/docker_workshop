# docker_workshop

![Image of Docker](https://nickjanetakis.com/assets/blog/cards/differences-between-a-dockerfile-docker-image-and-docker-container-001320c81dd8d2989df10d0bec36341fd6a94b043f6f9de1c26ee79eaf16e566.jpg)

1. Download and install Docker from https://www.docker.com/get-started

Activities

- [ ] Download and run alpine docker container

- [ ] Connect to container

- [ ] Create docker image (using dockerfile)

- [ ] push to docker repo

## Tricks

- [ ] work with docker container

```bash
#list containers
docekr ps -a

#stop and remove container
docker stop <conteinerID>
docker rm <conteinerID>
```

- [ ] work with docker images

```bash
#list images
docker images

#remove images
docekr rmi <image_id>
```

- [ ] find IP of docker container

```bash
DCIP=$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <my-container-name>)
```

- [ ] run bash on docker container

```bash
docker exec -i -t <conteinerID> /bin/bash
```


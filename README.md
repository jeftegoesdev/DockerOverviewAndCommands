# Commands Docker
- All informations about docker in the machine
  - docker info
- Show the Docker version information
  - docker --version
- Show running containers (Process status)
  - docker ps
  - docker ps -a # Show all
  - docker container ls -a
  - docker container ps -a
- List all images in local repository
  - docker images
- Pull (download) an image or a repository from a registry
  - docker pull `<image_name>:<version>` or `<tag>` # Example docker pull hello-world:latest
- Run a command in a new container
  - docker run `<image_name>` # Example docker run hello-world
  - docker run -d `<image_name>` # Run container in background and print container ID 
- Rum a command to stop a container
  - docker stop `<container_name>`
- Remove image
  - docker image rm `<image_name>` or `<image_id>` # Example docker image rm hello-world:latest
- Remove container
  - docker container rm `<container_name>` or `<container_id>`
- Fetch the logs of a container
  - docker logs -f `<image_name>`
- Run a command in a running container
  - docker exec -ti `<container_name>` bash # -ti --interactive and --tty
- Copy files/folders between a container and the local filesystem
  - docker cp `<file_name>` `<container_name>`:`<path>`/`<file_name>` # Example: docker cp script.sh myContainer:/tmp/script.sh

# Commands Docker Compose
- All informations about docker compose in the machine
  - docker-compose version
- Create and start containers, use docker-compose.yml
  - docker-compose up -d
- Stop all containers
  - docker-compose stop

# Docker Compose template
```
version: '3'
services:
  my_service:
    container_name: CONTAINER_NAME
    image: IMAGE_NAME
    ports:
      - "8080:8080"
    volumes:
      - "$PWD/HOME:/VAR/PATH_HERE"
    networks:
      - net
networks:
  net: 
```

# Images
## RabbitMQ image (http://localhost:15672/)
- docker pull rabbitmq:3-management
- docker run -d -p 15672:15672 -p 5672:5672 --name rabbit-test rabbitmq:3-management

## MsSql image (localhost,1445)
- docker pull mcr.microsoft.com/mssql/server:2019-latest
- docker run -d -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=yourStrong(!)Password" --name ordermssql -p 1445:1433 mcr.microsoft.com/mssql/server:2019-latest

## Jenkins image
- docker pull jenkins/jenkins
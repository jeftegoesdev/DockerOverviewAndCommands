# Commands
- All informations about docker in the machine
  - docker info
- Show the Docker version information
  - docker --version
- Show running containers
  - docker ps
- List all images in local repository
  - docker images
- Pull (download) an image or a repository from a registry
  - docker pull `<image_name>:<version>` or `<tag>` # Example docker pull hello-world:latest
- Run a command in a new container
  - docker run `<image_name>` # Example docker run hello-world
  - docker run -d `<image_name>` # Run container in background and print container ID 
- Rum a command to stop a container
  - docker stop `<container_name>`
- Remove one or more containers
  - docker image rm `<container_name>` # Example docker image rm hello-world:latest
  - docker rmi `<image_name>` or `<image_id>` # Example docker rmi hello-world:latest

# Docker compose model
```
version: '3'
services:
  jenkings:
    container_name: CONTAINER_NAME
    image: IMAGE_NAME
    ports:
      - "8080:8080"
    volumes:
      - "$PWD/HOME:/VAR/PATH_HERE"
    networks:
      - net
network:
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
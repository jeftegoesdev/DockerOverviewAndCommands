# Commands
- Show the Docker version information
  - docker --version
- List all images in local repository
  - docker images
- Pull (download) an image or a repository from a registry
  - docker pull `<image_name>:<version>` or `<tag>` # Example docker pull hello-world:latest
- Run a command in a new container
  - docker run `<image_name>` # Example docker run hello-world
- Remove one or more images
  - docker rmi `<image_name>` or `<image_id>` # Example docker rmi hello-world:latest

- docker run -p 15672:15672 -p 5672:5672 --name rabbit-test rabbitmq:3-management
# Terraform course

## Section 2: Start DevOps with Docker

Containerization is key
- makes devops very easy
- standardized application packaging (tech agnostic)
- multi platform support (only needs docker engine or container orchestration software)
- light-weight and isolation

Docker registry, usually docker hub
- stores docker images
- images accessed with a path REPOSITORY:TAG where tag is a version
- docker run command goes and fetches our application image from there
- docker hub is public and tracks application versions
- private registries are used for commercial applications
- log into docker hub, build image, then push

Docker terminology
- image is just information on how a container will be realized. A snapshot of an environment
- a running version of the image is a container. An environment with all the software running in it
- 5000:5000 maps the docker bridge port 5000 to the host port 5000
- use Dockerfile to build a docker image

Docker architecture
- Docker client takes commands and sends them to server component of docker
- Docker Daemon executes commands
  - managing images
  - running containers

Docker commands
- `docker search SOFTWARE_NAME` and look for Official -> OK for official images

Docker Network
- default network is bridge, which doesn't allow containers to talk to each other using localhost
- need to establish a link between containers using the --link and --env parameters
- second option is host, so all container ports are exposed and accessible on local host. Only works on linux
- recommended option: custom network. Create a custom network and use the --network parameter to make all containers run in the same network

Docker compose
- a tool for defining and running multi-container applications
- instead of Dockerfile, uses a docker-compose.yml file
- dockerfile defines images, docker-compose pulls images; and creates, configures and runs containers (docker-compose up)
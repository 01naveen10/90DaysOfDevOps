## Questions

- What is the Difference between an Image, Container and Engine?
A) 
    image: it is a template used to create a docker container.it contain application code dependencies and other files required to run the application
    Container: it is the run time instance of the docker image which is private from other containers
    Engine:It is responsible ofr building and running docker conatainers it contains docker daemon, api and cli

- What is the Difference between the Docker command COPY vs ADD?
A)
    COPY is used to save files from host to contaienr
    ADD is used to copy files from tar, url or other locations

- What is the Difference between the Docker command CMD vs RUN?
A)
    CMD : commands to execute while running container
    RUN : commands to run in the build image
  
- How Will you reduce the size of the Docker image?
A)   use mutli stage build, remove package, use light weight images, use .dockerignore

- Why and when to use Docker?
A)   it is useful in deploying applications across different environments for consistency and reliability
     it is used in microservice architecture

- Explain the Docker components and how they interact with each other.
A)    
      Docker contians docker daemon cli and api. Docker daemon is used to run images contianers etc, cli is used to interact with daemon and api
      docker files are used to make images and they are used to run contianers

- Explain the terminology: Docker Compose, Docker File, Docker Image, Docker Container?
A)    docker compose to run multi container docker images
      dockerfile: used to build docker image
      docker image: executable package used to create containers contians
      docker container: instance of docker image to run the application

- In what real scenarios have you used Docker?
A)    to run legacy applications, run ci cd pipelines, run across multiple systems

- Docker vs Hypervisor?
A)    docker uses containerization to virtualise the os envrionment and share resources from kernel whereas hypervisor will virtualise guest os and run. dockers are light weight and have faster start up time

- What are the advantages and disadvantages of using docker?
A)    advantages : light weigth faster start up easy to scale, simplified deployment, consistent across systems
      disadvantages : cannot acheive complete isolation, complexity in network and data management, less support ot windows

- What is a Docker namespace?
A)    allows isolation to resources from other containers and other applications 

- What is a Docker registry?
A)    storage to share and get docker images docker Hub is one such registry

- What is an entry point?
A)    specifies which command to run first

- How to implement CI/CD in Docker?
A)    Ci CD involves continous build deploying we can use docker images to run containers and jenkins and other tools to implement continous integration

- Will data on the container be lost when the docker container exits?
A)    yes as the dockers are ephemeral in nature so we cna use bind mount or volumes to make them persistent

- What is a Docker swarm?
A)    it is used for container orchestration of docker hosts  by  auto scaling, load balancing etc

- What are the docker commands for the following:
  - view running containers
  // docker ps
  - command to run the container under a specific name
  //docker docker run --name contname
  - command to export a docker
  //docker export name
  - command to import an already existing docker image
  //docker import name
  - commands to delete a container
  //docker rm name
  - command to remove all stopped containers, unused networks, build caches, and dangling images?
  //docker system prune
- What are the common docker practices to reduce the size of Docker Image?
A) use light weight images, remove unnecessary dependencies, use multi stage build, use .dockerignore to remove unnecessary fiels to be excluded from building dockerimage 
# Task-01

- Fork [this](https://github.com/LondheShubham153/node-todo-cicd.git) repository:
- Create a connection to your Jenkins job and your GitHub Repository via GitHub Integration.
- Read About [GitHub WebHooks](https://betterprogramming.pub/how-too-add-github-webhook-to-a-jenkins-pipeline-62b0be84e006) and make sure you have CICD setup
- Refer [this](https://youtu.be/nplH3BzKHPk) video for the entire project

A)
fork, launch ec2 instance >> install jenkins >> create job 
github link >> ssh-keygen in ec2 instance and share the public key in github ssh
job >>github link >>  add credentials 
ssh key pair >> username ubuntu key private key >>select in jenkins
>>after checking it is running then create Dockerfile for it 
Dockerfile
/////////////////////////////////////////////////
FROM node:12.2.0-alpine
WORKDIR app
COPY . .
RUN npm install
EXPOSE 8000
CMD ["node","app.js"]
/////////////////////////////////////////////////
docker build .  >> docker run -d --name name img
add jenkins to docker group in ec2 instance and chmod folder to 777
web hooks to detect changes and automatically build  >> github integration plugin >> project >> settings >>webhook >> url of jenkins/github-webhook/ && application/json
go to jenkins job and select trigger on poll git hook
make changes in github and check the build

# Task-02

- In the Execute shell run the application using Docker compose
- You will have to make a Docker Compose file for this Project (Can be a good open source contribution)
- Run the project and give yourself a treat:)

A) 
docker-compose.yaml
////////////////////////////////////////////////////////////////
version: '3.8'  # Docker Compose version

services:
  app:
    image: node:12.2.0-alpine
    working_dir: /app
    volumes:
      - .:/app
    ports:
      - "8000:8000"
    environment:
      - NODE_ENV=production
    command: sh -c "npm install && node app.js"
//////////////////////////////////////////////////////////////////
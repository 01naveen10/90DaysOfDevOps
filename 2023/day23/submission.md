# Task-01

- create a agent for your app. ( which you deployed from docker in earlier task)
- Create a new Jenkins freestyle project for your app.
- In the "Build" section of the project, add a build step to run the "docker build" command to build the image for the container.
- Add a second step to run the "docker run" command to start a container using the image created in step 3.

A)
new job 
docker build -t node-web -f /home/projects/simpe-nodejs-website/Dockerfile /home/projects/simpe-nodejs-website
docker run -d -p 3003:3000 node-web
build now

# Task-02

- Create Jenkins project to run "docker-compose up -d" command to start the multiple containers defined in the compose file (Hint- use day-19 Application & Database docker-compose file)
- Set up a cleanup step in the Jenkins project to run "docker-compose down" command to stop and remove the containers defined in the compose file.


A)
docker-compose.yaml
///////////////////////////////////////////////////////////////////////////////////////////
version: '3.8'  # Docker Compose version

services:
  # Node.js web application service
  web:
    image: node:14  # Base Node.js Docker image
    volumes:
      - ./app:/app   # Mount the local 'app' directory to '/app' in the container
    ports:
      - "3000:3000"  # Expose port 3000 on the host and map it to port 3000 in the container
    environment:
      NODE_ENV: production  # Set Node.js environment to production
    command: npm start  # Command to start the Node.js application

  # MongoDB database service
  db:
    image: mongo:4.4  # Base MongoDB Docker image
    deploy:
      replicas: 3
    volumes:
      - mongodb_data:/data/db  # Mount a volume for MongoDB data storage
    ports:
      - "27010-27017:27017"  # Expose port 27017 on the host and map it to port 27017 in the container

volumes:
  mongodb_data:  # Define a named volume for MongoDB data storage
///////////////////////////////////////////////////////////////////////////////////////////

sudo docker-compose -f filelocation/docker-compose.yaml up -d
sudo docker-composer if filelocation/docker.composer.yaml down
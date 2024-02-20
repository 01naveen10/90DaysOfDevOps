## Tasks
docker docker-compose cheatsheet
A)
docker ps -a


////////  DOCKER IMAGE  /////////////
docker pull
docker push usr/na:1.0
docker rmi
docker images
docker image prune -a
docker build . -t tagname
docker save img > imgg.tar
docker load -i imgg.tar

////////  DOCKER STATS  ///////////
docker logs
docker stats
docker top
docker inspect
docker diff
docker port

////////  DOCKER CONTAINERS  ///////////
docker ps -a
docker rm -f
docker stop 
docker start
docker cp app:/src/file dest
docker exec -it
docker commit  //create image out of container
docker rename oldname newname

////////  DOCKER RUN  ///////////
docker run -d --name name1 -p port  --hostname  --entrypoint


////////  DOCKER COMPOSE  ///////////
docker-compose up
docker-compose down
docker-compose start
docker-compose stop
docker-compose pause
docker-compose unpause

sample docker-compose.yaml
version: '3'

services:
  app:
    image: node:16-alpine
    working_dir: /app
    volumes:
      - myvol:/app/data
    command: npm start
    ports:
      - "8081:8080"
    depends_on:
      - db


  db:
    image: redis:alpine
    deploy:
      replicas: 2
    ports:
      - "6370-6379:6379"

volumes:
  my_vol:
    external: true





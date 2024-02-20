
## Task-1

- Create a multi-container docker-compose file which will bring _UP_ and bring _DOWN_ containers in a single shot ( Example - Create application and database container )

_hints:_

- Use the `docker-compose up` command with the `-d` flag to start a multi-container application in detached mode.
- Use the `docker-compose scale` command to increase or decrease the number of replicas for a specific service. You can also add [`replicas`](https://stackoverflow.com/questions/63408708/how-to-scale-from-within-docker-compose-file) in deployment file for _auto-scaling_.
- Use the `docker-compose ps` command to view the status of all containers, and `docker-compose logs` to view the logs of a specific service.
- Use the `docker-compose down` command to stop and remove all containers, networks, and volumes associated with the application

A)  docker deploy replicas and port range so the containers can access it from ost to the smae port in the container 
    ports: "6370-6379:6379"

## Task-2

- Learn how to use Docker Volumes and Named Volumes to share files and directories between multiple containers.
- Create two or more containers that read and write data to the same volume using the `docker run --mount` command.
- Verify that the data is the same in all containers by using the docker exec command to run commands inside each container.
- Use the docker volume ls command to list all volumes and docker volume rm command to remove the volume when you're done.

A) docker volume create my_vol
    docker run -d --name containee1 --mount source=my_vol,target=/data alpine tail -f /dev/null
    docker run -d --name containee2 --mount source=my_vol,target=/data alpine tail -f /dev/null

    docker exec -it container1 sh
    echo "Hello from container1" > /data/file1.txt
    exit

    docker exec -it container2 sh
    cat /data/file1.txt

    docker volume ls
    docker volume rm my_vol

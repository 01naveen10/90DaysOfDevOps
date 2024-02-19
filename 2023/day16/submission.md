# Tasks

As you have already installed docker in previous days tasks, now is the time to run Docker commands.

- Use the `docker run` command to start a new container and interact with it through the command line. [Hint: docker run hello-world]
A) done

- Use the `docker inspect` command to view detailed information about a container or image.
A) done

- Use the `docker port` command to list the port mappings for a container.
A) done

- Use the `docker stats` command to view resource usage statistics for one or more containers.
A) done

- Use the `docker top` command to view the processes running inside a container.
A) done

- Use the `docker save` command to save an image to a tar archive.
A) done

- Use the `docker load` command to load an image from a tar archive.
A) done

//////////////////////////////////////////////////////////////////////
1.) download the python project and install django and run the app in virutalenv and localhost then
2.) go to ec2 clone the git repo install djnago if not installed and run the manage.py runserver
3.) set the run server to run on 0.0.0.0 instead of local host then set the port to 8001 or someother
4.) allow the port access in security groups >> http >> allowed hosts in settings.py allowed host to '*'
5.) use nohup python3 mange....:8001 to run it in the background and use lsof -i:8001 to get information about process ID on which the application is running and using kill -9 PID command to stop that server

---
6.) install docker.io then go to the project and create Dockerfile and run the commands which are needed to run the application like FROM python3 image install django version then copy the files from the main file to container and then run migate command then commands as array [python manage.py runserver 0.0.0.0:8001] 
7.) docker build the image -t imageName >> docker run -p 8001:8001 imageID  // -p for port mapping of container to ec2 instance 
8.) -d in docker run to run daemon in background
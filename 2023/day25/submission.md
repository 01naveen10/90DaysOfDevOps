# Task-01

- Document the process from cloning the repository to adding webhooks, and Deployment, etc. as a README , go through [this example](https://github.com/LondheShubham153/fynd-my-movie/blob/master/README.md)

- A well written readme file will help others to understand your project and you will understand how to use the project again without any problems.

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

- Also it's important to keep smaller goals, as its a small task, think of a small Goal you can accomplish.

- Write about it using [this template](https://www.linkedin.com/posts/shubhamlondhe1996_taking-resolutions-and-having-goals-for-an-activity-7023858409762373632-s2J8?utm_source=share&utm_medium=member_desktop)

Goal:finish 90daysofdevops challenge by this month end  or by march 15th
Strategy: keep doing it
note to self: u can do it . don't procastinate
reward: knoweledge about devops tools and flow can switch to devops field
task:

- Create a Dockerfile for a simple web application (e.g. a Node.js or Python app)
A)
FROM node:16-alpine
COPY . .
RUN npm install
CMD ["node", "server.js"]

- Build the image using the Dockerfile and run the container
A) docker run -p 3000:3000 simple-nodejs-wesite

- Verify that the application is working as expected by accessing it in a web browser
A) done

- Push the image to a public or private repository (e.g. Docker Hub )
A) https://hub.docker.com/repository/docker/01naveen10/simple-nodejs-website/general

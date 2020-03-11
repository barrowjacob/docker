#THE FOLLOWING RUNS AUTOMATICALLY WHEN YOU TYPE "docker image built -t NAME_YOUR_IMAGE_HERE"
#see https://docs.docker.com/get-started/part2/ for more details



FROM node:current-slim
#Start FROM the pre-existing node:current-slim image. This is an official image, built by the node.js vendors and validated by Docker to be a high-quality image containing the Node.js Long Term Support (LTS) interpreter and basic dependencies.

WORKDIR /usr/src/app
#Use WORKDIR to specify that all subsequent actions should be taken from the directory /usr/src/app in your image filesystem (never the host’s filesystem).
COPY package.json .
#COPY the file package.json from your host to the present location (.) in your image (so in this case, to /usr/src/app/package.json)
RUN npm install
#RUN the command npm install inside your image filesystem (which will read package.json to determine your app’s node dependencies, and install them)
EXPOSE 8080
#The EXPOSE 8080 informs Docker that the container is listening on port 8080 at runtime.
CMD [ "npm", "start" ]
#The CMD directive is the first example of specifying some metadata in your image that describes how to run a container based on this image. In this case, it’s saying that the containerized process that this image is meant to support is npm start.
COPY . .
#COPY in the rest of your app’s source code from your host to your image filesystem.
# Pulling the parent image from our desktop or dockerHub
FROM node:16-alpine

#Installing nodemon globally  
RUN npm install -g nodemon

# It tells docker when we run commands on the image in future to do it from this working directory 
WORKDIR /app
# copying the source code to a specific path not the root to avoid clash with other files
COPY package.json .
RUN npm install
COPY . .
# installing all the dependencies 
# this run instruction tells docker to run a command on the image itself as this layer added
# on while the image is being built
# We need to run our command in the same directory as our package.json


# instruction tells docker which port the container expose (the port of the computer will be owned)
# by the container (optional)
EXPOSE 4000

# To specify the commands that should run at the run time of the instance of the image inside
# the container, and not at the build time
CMD ["npm", "run","dev"]
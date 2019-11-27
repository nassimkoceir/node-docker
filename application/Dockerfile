# Get base image with light base system Alpinehttps://github.com/nassimkoceir/starting-nodejs
FROM node:12-alpine

# Create and grant permission to node_modules and app folders
# App folder is the directory where our source code will be stored within the docker
# node_module folder is the directory where module will be stored
RUN mkdir -p /node/app/node_modules && chown -R node:node /node/app

# Set working directory
WORKDIR /node/app

# Copy the source code to the Docker container /!\ CHANGE ./DIRECTORY with the name of where your source code is located
COPY ./DIRECTORY/ ./

# Install nodemon to automatically watch changes to serverside node.js file
RUN npm install -g nodemon

# Install dependencies from package.json
RUN npm install

# Set the container to be visible on the 8080 port (so other services can access the container on this port)
EXPOSE 8080

# Run a command at boot to start the NodeJS server using nodemon (ONLY FOR DEVELOPMENT)
CMD ["nodemon","app.js"]

## In production, use this instead of previous command (ONLY FOR PRODUCTION)
# CMD ["npm", "start"]

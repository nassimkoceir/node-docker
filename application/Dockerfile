# Get base image with light base system Alpinehttps://github.com/nassimkoceir/starting-nodejs
FROM node:12-alpine

# Create and grant permission to node_modules and app folders
# App folder is the directory where our source code will be stored
# node_module folder is the directory where module will be stored
RUN mkdir -p /node/app/node_modules && chown -R node:node /node/app

# Set working directory
WORKDIR /node/app

# Copy the source code to the Docker container /!\ CHANGE ./DIRECTORY with is the name of your github repository
COPY ./DIRECTORY/ ./

# Install nodemon to watch changes in local git repository (ONLY FOR DEVELOPMENT)
RUN npm install -g nodemon

# Install dependencies from package.json
RUN npm install

# Set the container to be visible on the 8080 port (to access the container)
EXPOSE 8080

# Run a command at boot to start the NodeJS server using nodemon (ONLY FOR DEVELOPMENT)
CMD ["nodemon","app.js"]

## In production, use this instead of previous command (ONLY FOR PRODUCTION)
# CMD ["npm", "start"]

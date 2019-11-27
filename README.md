# Node-docker (FOR DEVELOPMENT PURPOSE ONLY)
BeCode-Made Docker container for NodeJS

This docker is for development purpose. It's not safe to use this in production as
the environment variables are in this repository for everyone to see.
As long as it runs on your own machine the unsafe logins and passwords are
fine, but don't throw it online as is. You don't need to be a l33T haXX0r to
guess "root root". 

The Dockerfile contains some adaptations which can easily transform it into a
production container, but the docker-compose and docker.env must be rewritten
and not used as is. 

## 1. How to use this ?
- Clone this repo to your machine. This should copy the files and create a folder called "application".
- Copy the code you wish to run in this Docker inside of the "application" folder, either from somewhere else in your machine or a github repository you want to work on within the docker.
- You will find in the "docker-compose.yml" several places where "_DIRECTORY_" is written in all caps. You need to adapt this line: in place of "_./application/DIRECTORY_" write the path to the root of your code.
- In the Dockerfile there is also a "_DIRECTORY_" in all caps. Here you also
  need to put the name of the folder where you have your source code, relative
to the Dockerfile. If you pasted your files directly into the "application"
folder, just write  `.`. 
- Copy/Paste the "package.json", the "app.js" and the ".gitignore" from _DIRECTORY_ at the root of your code, unless you already have yours. The app.js is the serverside node.js code. You cannot rename this file, unless you enter the node container, stop and restart nodemon.
- Type the following command to start the docker: 
```
sudo docker-compose up 
```
This will give you the full output of the errors and occupy a terminal window. 
- Alternatively, use:
```
sudo docker-compose up -d
```
This will liberate your terminal window after starting the containers but will not give you a good look at possible errors.

- Add the dependencies you need in the package.json, enter the container and install them.

*Note*

This container comes with no node modules pre-installed. If/when you need them,
enter node docker container and install as needed. You only need to do this once.

## 2. What was the project ?
The goal was to understand the usage of Docker and Docker-Compose.

## 3. What containers does this Docker use ?
- Node 12 with an Alpine subsystem (node.js container)
- MongoDB (latest) (database container)
- Mongo-Express (latest) (database manager container)

## 4. How to collaborate ?
You can pull request the project. ;)

## 5. Collaborators
- Nassim Koceir (Founder)
- Marvin Louis (Coach / Teacher / Debugger / Tech Support)
- Octavia Couneson (Translator / Debugger)
- Laly Singh (Beta-Tester / Translator)
- Gregoire Wastelain (Beta-Tester)

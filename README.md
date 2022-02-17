## Docker -It's a tool for managing containers
## 1. Images and Containers

### Images
##### Features
- Blue print for containers
- They're read only (can not be edited, only a new one can be created)
##### They store
- Runtime environment e.g specific node version
- Source/Application code
- Any Dependencies
- Extra configuration eg. env variables
- Other commands
##### Image Structure
1. Parent Image-  Includes the OS & sometimes the runtime environment
2. Source code
3. Dependencies
4. Configs - eg ports, volumes

### DOCKER FILE 
#### commands
##### FROM node:16-alpine 
###### - parent image

#### WORKDIR /app 
###### - working directory

#### COPY package.json .
###### - copies package.json to WORKDIR to enable Layer Caching and increase speed of Image build process / layer caching

#### RUN npm/yarn install 
###### - Install project dependencies

#### COPY . . 
###### - copies the project files/folder to the working directory

#### EXPOSE 4000 (not compulsory but recommended)
###### - specifies the port the project will run on

#### CMD ["npm", "run", "dev"]
###### - command to run the project from package.json (npm run dev)


### Containers
- Are runnable instances of images
##### Features
- Runs our application as outlined by a docker image
- Its completly isolated from any other processes in our computer (Isolate Process)


### Containers

## 2. Parent Images and Docker Hub
## 3. Dockerfile
## 4. .dockerignore
###### Ignore files such as node_modules or idea folders
## 5. starting and stopping containers

## 6. Layer Caching
##### N/B: Docker Layer Caching - prevents re-downloading dependencies from package.json if it already downloaded. This is done by adding copying the package.json file to the working dir, installing dependencies, then copying the projects folder to the WORKDIR
##### FROM node:16-alpine
###### WORKDIR /app
###### COPY package.json .
###### RUN npm/yarn install
###### COPY . .
###### EXPOSE 4000
###### CMD ["npm", "run", "dev"]

## 7. Managing Images and Containers
### Images (commands)

##### $ docker images = shows list of images
##### $ docker image rm <imagename> = deletes an image
##### $ docker image rm <imagename> -f = deletes an image regardless if its being used in/by a container

### Containers(commands)

##### $ docker ps = shows list of containers runnning
##### $ docker ps -a = shows list of containers
##### $ docker container rm <containername> = deletes/removes a container

### To delete all Images and Containers 
####  $ docker system prune -a





## 8. Volumes
## 9. Docker compose
(credits: The Net Ninja)

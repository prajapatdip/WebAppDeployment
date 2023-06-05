# Web Application Deployment on Dockerhub

In this project I have taken a Web Application which is made of:

    1. HTML.
    2. JavaScript.
The Application uses Node.js for the server.

In this project I make a connection between the Web Application and MonogoDB for database using Docker on the local host server. This application is a simple personal profile application in which you can update information as many time as you want and the updates will remains as it is after refreshing the page and the last information present befor update will be store in the MonogoDB database. I deployed the application and Monogo-express on the local host. I create mongo.yaml file of MonogoDB and Monogo-express for deployement on local host and runnig the container. I also created docker image using Dockerfile its for easyness using this image you do all this process in one click. Requirements:

    1. YMAL language.
    2. Docker commands.

![application](https://github.com/prajapatdip/WebAppDeployment/blob/main/images/Web%20Image.png)

![database](https://github.com/prajapatdip/WebAppDeployment/blob/main/images/Database.png)
## Run Locally


```bash
    git clone https://github.com/prajapatdip/WebAppDeployment.git
    cd WebAppDeployment

    docker build -t my-app .
    docker run -d -p 3000:3000 my-app
```
#### Starting MongoDB

```bash
    docker run -d/
    -p 27017:27017/
    -e MONGO_INITDB_ROOT_USERNAME=admin/
    -e MONGO_INITDB_ROOT_PASSWORD=password/
    --network mongo-network/
    --name mongodb/
    mongo
```

#### Starting Mongo-Express

```bash
    docker run -d/
    -p 8081:8081/
    -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin/
    -e ME_CONFIG_MONGODB_ADMINPASSWORD=password/
    -e ME_CONFIG_MONGODB_SERVER=mongodb/
    --network mongo-network/
    --name mongo-express/
    mongo-express
```

##### After Running all of this paste this two links on the local browser on different tabs

```bash
    1. http://localhost:3000
    2. http://localhost:8081
```

##### Enter Username and Password on mongo-express

```bash
    Username: admin
    Password: password
    Database name: my-db (Enter database name after logged in)
```
Now whenever you edit your profile and save it then previous data will be visible to you on mongo-express
## Docker Image

https://hub.docker.com/repository/docker/prajapatdip/getting-started/general

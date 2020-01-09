# Node.JS, Express, Jade, and MongoDB

A tutorial and complete sample project for Front-End developers showing how to get Node, Express and Jade up and running, connected to MongoDB, and reading from / writing to the database and running on docker.

## Quickstart

If you want to run this example code, you will need to do an NPM Install, as the node_modules directory has been removed from this repository. You'll also need to set up a MongoDB database. I highly recommend just going through the tutorial!


## Contents

* /public - static directories suchs as /images
* /routes - route files for tutorial project
* /views - views for tutorial project
* README.md - this file
* app.js - central app file for tutorial project
* package.json - package info for tutorial project

##Steps for using locally:

* npm install
* in the app.js file change 'mongo:27017/nodetest1' to 'localhost:27017/nodetest1'

##Steps for using with docker:

* docker-compose up

 > if files has been changed:
 * docker-compose up --build


## additional info for data persistance

* put > volumes:
      - ./data:/data/db 
      in the docker-compose.yml file in the mongo service section

## Info to run container from image

* docker build -t myapp .    // command to build image from dockerfile with name myapp, please mind the .

* replace build: . with image: anmolsinha1793/node_express_mongo_demo:initial in the docker-compose.yml file in the app service section

## Steps to run container in docker network

* docker network create knote      //knote is the name of the network if changed please change everywhere below after --network

* docker run --name=mongo --rm  --network=knote mongo   //last mongo is the name of the image

* docker run --name=demo-app  --rm  --network=knote  -p 3000:3000  -e MONGO_URL=mongodb://mongo:27017/dev  my-app  //my-app is the name of the image

* docker run --name=demo-app --rm  --network=knote -p 3000:3000 -e MONGO_URL=mongodb://mongo:27017/dev anmolsinha1793/demo:1.0.0   //anmolsinha1793/demo:1.0.0 is the name of the image to be pulled from repository

## Info to deploy application using minikube(local kubernetes cluster for development)

* minikube start

* minikube status  // to make sure that your Minikube cluster is running

* kubectl apply -f kube // submit your resource definitions to Kubernetes where kube is the folder name which consists of manifest files

* kubectl get pods --watch  // to watch pods status takes some time to update

* minikube service myapp // The command should open the URL of the myapp Service in a web browser

* kubectl scale --replicas=3 deployment/myapp  // run this command for scaling where myapp is the name given to deployment in manifest file

* minikube dashboard //in order to get a UI view of kubernetes and better understanding


## For references on kubernetes with minikube

* https://learnk8s.io/nodejs-kubernetes-guide

* https://rominirani.com/tutorial-getting-started-with-kubernetes-on-your-windows-laptop-with-minikube-3269b54a226
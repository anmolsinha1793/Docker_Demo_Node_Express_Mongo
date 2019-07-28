# Node.JS, Express, Jade, and MongoDB

A tutorial and complete sample project for Front-End developers showing how to get Node, Express and Jade up and running, connected to MongoDB, and reading from / writing to the database and running on docker.

## Quickstart

[Visit the tutorial online](https://closebrace.com/tutorials/2017-03-02/the-dead-simple-step-by-step-guide-for-front-end-developers-to-getting-up-and-running-with-nodejs-express-and-mongodb). The rest of the project is provided just to show the functioning finished results. The tutorial will show you how to build all of this stuff, from downloading Node all the way to the end.

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


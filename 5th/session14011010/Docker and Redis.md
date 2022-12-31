#Docker and Redis
-----------------------------

#step1


### - Explanation about stack overflow

### - How to work with stack overflow and ...

### - Modifying the build of the pairmatching project

### - Explaining the process of nginx, docker

### -Bringing up a redis with Docker and reading data from it


--------------------------------

#step2

### How to bring up an express, redis and read a number from redis and add it every time the page is refreshed


First, create a package.json file


-------------------------


### package.json

{

"name": "redisnode",

"version": "1.0.0",

"description": "",

"main": "index.js",

"scripts": {

"test": "echo \"Error: no test specified\" && exit 1",

"start": "node index.js"

},

"keywords": [],

"author": "",

"license": "ISC",

"dependencies":{"express":"*",

"redis":"2.8.0"

}

}

----------------------------------------


### index.js



const redis = require("redis");

const express = require("express");

  
  

const app = express();

const client = redis.createClient({

host:"redis-server2",

port:6379,

  
  
  

});

  

client.set("visitnumber",0);

  

app.get("/",(req,res)=>{

  

client.get("visitnumber",(error,visits)=>{

res.send("click number" + visits);

client.set("visitnumber",parseInt(visits)+1);

  

})

  

})

  
  

app.listen(9600,()=>{console.log("salam mobina");})



---------------------------------


### Dockerfile

  

FROM hub.hamdocker.ir/node:alpine

  

WORKDIR /usr/app

COPY . .

  

RUN npm install

CMD ["npm", "start"]




------------------------------

	

### docker-compose.yml

version : "3"

services:

redis-server2:

image: "redis"

express2:

build: .

ports:

- "9600:9600"

*****************************************************
----------------
#step3

### Pairmatching Project 


Modify your dockerfile as below






FROM hub.hamdocker.ir/node:alpine as mywebpack

WORKDIR /app

COPY ./package*.json /app/

RUN npm install

COPY ./ /app/

RUN npm run build

# ---------------------------

FROM hub.hamdocker.ir/nginx:alpine

  

COPY --from=mywebpack /app/dist /usr/share/nginx/html

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

  

EXPOSE 80



-------------------------------------------------

Written by Mobina Esmaeili

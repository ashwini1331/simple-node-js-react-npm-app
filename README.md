Steps 1 - Install Node Js on Ubuntu Machine
sudo apt update

sudo apt install nodejs

sudo apt install npm

nodejs -v  // To check the node JS version 
Step 2 - Download the Publish Over SSH plugins
Key -- define the private Key ( you will get from .pem while when you will open as text file)

ssh Server - 

Name - define the name of the server.
HostName - Provide the IP address of your server.
UserName - Provide the user name here ex. if we are using Ubuntu ec2 instance then username is ubuntu

Click Save and Apply 
Step 3 - Create the Free Style Node JS project .
Git URL - https://github.com/Abhishek08/node-js...

WebHook Connection URL - http://IPADDRESS/github-webhook/ (push)

BUILD - npm install  // to download all the dependecines 
      - npm test  // to perform test case execution 

tar czf Node.tar.gz node_modules index.js package.json public app.json     
Step 4 - Post Build Action Define below details.
Source file : **/*.gz 

Exec Command 

mv ./home/ubuntu/one/node-js-sample/Node.tar.gz /home/ubuntu/test/Node.tar.gz;
cd /home/ubuntu/test/
tar -xf Node.tar.gz ;
docker rmi nodeimage;
docker stop nodecontainer;
docker rm nodecontainer;
docker build -t nodeimage .;
docker run -d --name nodecontainer -p 5001:5000 nodeimage;
Step 5 - Docker File in Node Js server
FROM node:latest

MAINTAINER Abhishek Modi 

RUN echo "Tryin to build my first application"

COPY . /var/www

WORKDIR /var/www

RUN npm install

EXPOSE 3000

ENTRYPOINT ["npm","start"]
###############################################################################################################################################################
### This repository is no longer maintained!

**For the most up to date test app to get you started on Heroku, head on over to [`node-js-getting-started`](https://github.com/heroku/node-js-getting-started).**

---

# node-js-sample

A barebones Node.js app using [Express 4](http://expressjs.com/).

## Running Locally

Make sure you have [Node.js](http://nodejs.org/) and the [Heroku Toolbelt](https://toolbelt.heroku.com/) installed.

```sh
git clone git@github.com:heroku/node-js-sample.git # or clone your own fork
cd node-js-sample
npm install
npm start
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```
heroku create
git push heroku master
heroku open
```

Alternatively, you can deploy your own copy of the app using the web-based flow:

[![Deploy to Heroku](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

## Documentation

For more information about using Node.js on Heroku, see these Dev Center articles:

- [10 Habits of a Happy Node Hacker](https://blog.heroku.com/archives/2014/3/11/node-habits)
- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Node.js on Heroku](https://devcenter.heroku.com/categories/nodejs)
- [Using WebSockets on Heroku with Node.js](https://devcenter.heroku.com/articles/node-websockets)

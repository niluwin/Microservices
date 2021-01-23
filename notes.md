# The Best Way to Set Up Docker for Your OS

## Docker for Windows 10 Pro/Ent: Setup and Tips

http://store.docker.com

docker version

cd .\udemy-docker-mastery\

docker ps

docker info

## Docker Toolbox for Windows 7, 8 and 10 Home: Setup and Tips

http://store.docker.com

cd .\udemy-docker-mastery\

docker-machine ls

docker-machine start

docker-machine help

docker-machine env default

docker version

## Docker for Mac Setup and Tips

http://store.docker.com

docker version

http://github.com/BretFisher/udemy-docker-mastery

docker version

docker container

docker container run --

docker

docker pause

## Docker for Linux Setup and Tips

docker

http://get.docker.com

curl -fsSL get.docker.com -o get-docker.sh

sh get-docker.sh

sudo usermod -aG docker bret

sudo docker version

docker version

sudo docker version

docker-machine version

http://github.com/docker/compose

http://github.com/docker/compose/releases

curl -L https://github.com/docker/compose/releases/download/1.15.0/docker-compose- `uname -s `- `uname -m` >/usr/local/bin/docker-compose

docker-compose version

http://github.com/docker/machine/releases

http://github.com/BretFisher/udemy-docker-mastery

git clone https://github.com/Bretfisher/udemy-docker-mastery.git

cd udemy-docker-mastery/

docker image

docker image ls --

# Creating and Using Containers Like a Boss

## Check Our Docker Install and Config

docker version

docker info

## Starting a Nginx Web Server

docker container run --publish 80:80 nginx

docker container run --publish 80:80 --detach nginx

docker container stop 690

docker container ls

docker container ls -a

docker container run --publish 80:80 --detach --name webhost nginx

docker container ls -a

docker container logs webhost

docker container top

docker container top webhost

docker container --help

docker container ls -a

docker container rm 63f 690 ode

docker container ls

docker container rm -f 63f

docker container ls -a

## Container VS. VM: It's Just a Process

docker run --name mongo -d mongo

docker ps

docker top mongo

docker stop mongo

docker ps

docker top mongo

docker start mongo

docker ps

docker top mongo

## Assignment Answers: Manage Multiple Containers

docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=yes MYSQL_RANDOM_ROOT_PASSWORD

docker container logs db

docker container run -d --name webserver -p 8080:80 httpd

docker ps

docker container run -d --name proxy -p 80:80 nginx

docker ps

docker container ls

docker container stop TAB COMPLETION

docker ps -a

docker container ls -a

docker container rm

docker ps -a

docker image ls

## What's Going On In Containers: CLI Process Monitoring

docker container run -d --name nginx nginx

docker container run -d --name mysql -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql

docker container ls

docker container top mysql

docker container top nginx

docker container inspect mysql

docker container stats --help

docker container stats

docker container ls

## Getting a Shell Inside Containers: No Need for SSH

docker container run -help

docker container run -it --name proxy nginx bash

docker container ls

docker container ls -a

docker container run -it --name ubuntu ubuntu

docker container ls

docker container ls -a

docker container start --help

docker container start -ai ubuntu

docker container exec --help

docker container exec -it mysql bash

docker container ls

docker pull alpine

docker image ls

docker container run -it alpine bash

docker container run -it alpine sh

## Docker Networks: Concepts for Private and Public Comms in Containers

docker container run -p 80:80 --name webhost -d nginx

docker container port webhost

docker container inspect --format '{{ .NetworkSettings.IPAddress }}' webhost

## Docker Networks: CLI Management of Virtual Networks

docker network ls

docker network inspect bridge

docker network ls

docker network create my_app_net

docker network ls

docker network create --help

docker container run -d --name new_nginx --network my_app_net nginx

docker network inspect my_app_net

docker network --help

docker network connect

docker container inspect TAB COMPLETION

docker container disconnect TAB COMPLETION

docker container inspect

## Docker Networks: DNS and How Containers Find Each Other

docker container ls

docker network inspect TAB COMPLETION

docker container run -d --name my_nginx --network my_app_net nginx

docker container inspect TAB COMPLETION

docker container exec -it my_nginx ping new_nginx

docker container exec -it new_nginx ping my_nginx

docker network ls

docker container create --help

## Assignment Answers: Using Containers for CLI Testing

docker container run --rm -it centos:7 bash

docker ps -a

docker container run --rm -it ubuntu:14.04 bash

docker ps -a

## Assignment Answers: DNS Round Robin Testing

docker network create dude

docker container run -d --net dude --net-alias search elasticsearch:2

docker container ls

docker container run --rm -- net dude alpine nslookup search

docker container run --rm --net dude centos curl -s search:9200

docker container ls

docker container rm -f TAB COMPLETION

# Container Images, Where To Find Them and How To Build Them

## The Mighty Hub: Using Docker Hub Registry Images

[Docker Image Specification v1.0.0](https://github.com/moby/moby/blob/master/image/spec/v1.md)

http://hub.docker.com

docker image ls

docker pull nginx

docker pull nginx:1.11.9

docker pull nginx:1.11

docker pull nginx:1.11.9-alpine

docker image ls

## Images and Their Layers: Discover the Image Cache

docker image ls

docker history nginx:latest

docker history mysql

docker image inspect nginx

## Image Tagging and Pushing to Docker Hub

docker image tag -- help

docker image ls

docker pull mysql/mysql-server

docker image ls

docker pull nginx:mainline

docker image ls

docker image tag nginx bretfisher/nginx

docker image tag --help

docker image ls

docker image push bretfisher/nginx

docker --help

docker login

cat .docker/config.json

docker image push bretfisher/nginx

docker image push bretfisher/nginx bretfisher/nginx:testing

docker image ls

docker image push bretfisher/nginx:testing

docker image ls

## Building Images: The Dockerfile Basics

cd dockerfile-sample-1

vim Dockerfile

## Building Images: Running Docker Builds

docker image build -t customnginx .

docker image ls

docker image build -t customnginx .

## Building Images: Extending Official Images

cd dockerfile-sample-2

vim Dockerfile

docker container run -p 80:80 --rm nginx

docker image build -t nginx-with-html .

docker container run -p 80:80 --rm nginx-with-html

docker image ls

docker image tag --help

docker image tag nginx-with-html:latest bretfisher/nginx-with-html:latest

docker image ls

docker push

## Assignment Answers: Build Your Own Dockerfile and Run Containers From It

cd dockerfile-assignment-1

vim Dockerfile

docker build cmd

docker build -t testnode .

docker container run --rm -p 80:3000 testnode

docker images

docker tag --help

docker tag testnode bretfisher/testing-node

docker push --help

docker push bretfisher/testing-node

docker image ls

docker image rm bretfisher/testing-node

docker container run --rm -p 80:3000 bretfisher/testing-node

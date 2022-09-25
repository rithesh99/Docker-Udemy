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

docker-machine ls

docker version

docker version

docker-machine ls

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

docker

docker container run

docker run

## Starting a Nginx Web Server

docker container run --publish 80:80 nginx

docker container run --publish 80:80 --detach nginx

docker container ls

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

# Container Lifetime & Persistent Data: Volumes, Volumes, Volumes

## Persistent Data: Data Volumes

docker pull mysql

docker image inspect mysql

docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql

docker container ls

docker container inspect mysql

docker volume ls

docker volume inspect TAB COMPLETION

docker container run -d --name2 mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True mysql

docker volume ls

docker container stop mysql

docker container stop mysql2

docker container ls

docker container ls -a

docker volume ls

docker container rm mysql mysql2

docker volume ls

docker container run -d --name mysql -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql mysql

docker volume ls

docker volume inspect mysql-db

docker container rm -f mysql

docker container run -d --name mysql3 -e MYSQL_ALLOW_EMPTY_PASSWORD=True -v mysql-db:/var/lib/mysql mysql

docker volume ls

docker container inspect mysql3

docker volume create --help

## Persistent Data: Bind Mounting

cd dockerfile-sample-2

pcat Dockerfile

docker container run -d --name nginx -p 80:80 -v $(pwd):/usr/share/nginx/html nginx

docker container run -d --name nginx2 -p 8080:80 nginx

docker container exec -it nginx bash

## Assignment Answers: Edit Code Running In Containers With Bind Mounts

docker run -p 80:4000 -v $(pwd):/site bretfisher/jekyll-serve

# Making It Easier with Docker Compose: The Multi-Container Tool

## Docker Compose and The Docker-compose.yml File

docker-compose.yml

https://docs.docker.com

## Trying Out Basic Compose Commands

pcat docker-compose.yml

docker-compose up

docker-compose up -d

docker-compose logs

docker-compose --help

docker-compose ps

docker-compose top

docker-compose down

## Assignment Answers: Build a Compose File for a Multi-Container Service

docker-compose.yml

docker pull drupal

docker image inspect drupal

docker-compose up

https://hub.docker.com

docker-compose down --help

docker-compose down -v

## Adding Image Building to Compose Files

docker-compose.yml

docker-compose up

docker-compose up --build

docker-compose down

docker image ls

docker-compose down --help

docker image rm nginx-custom

docker image ls

docker-compose up -d

docker image ls

docker-compose down --help

docker-compose down --rmi local

## Assignment Answers: Compose for Run-Time Image Building and Multi-Container Dev

docker-compose up

docker-compose down

docker-compose up

# Swarm Intro and Creating a 3-Node Swarm Cluster

## Create Your First Service and Scale it Locally

docker info

docker swarm init

docker node ls

docker node --help

docker swarm --help

docker service --help

docker service create alpine ping 8.8.8.8

docker service ls

docker service ps frosty_newton

docker container ls

docker service update TAB COMPLETION --replicas 3

docker service ls

docker service ps frosty_newton

docker update --help

docker service update --help

docker container ls

docker container rm -f frosty_newton.1.TAB COMPLETION

docker service ls

docker service ps frosty_newton

docker service rm frosty_newton

docker service ls

docker container ls

## Creating a 3-Node Swarm Cluster

http://play-with-docker.com

docker info

docker-machine

docker-machine create node1

docker-machine ssh node1

docker-machine env node1

docker info

http://get.docker.com

docker swarm init

docker swarm init --advertise-addr TAB COMPLETION

docker node ls

docker node update --role manager node2

docker node ls

docker swarm join-token manager

docker node ls

docker service create --replicas 3 alpine ping 8.8.8.8

docker service ls

docker node ps

docker node ps node2

docker service ps sleepy_brown

## Scaling Out with Overlay Networking

docker network create --driver overlay mydrupal

docker network ls

docker service create --name psql --netowrk mydrupal -e POSTGRES_PASSWORD=mypass postgres

docker service ls

docker service ps psql

docker container logs psql TAB COMPLETION

docker service create --name drupal --network mydrupal -p 80:80 drupal

docker service ls

watch docker service ls

docker service ps drupal

docker service inspect drupal

# Swarm Basic Features and How to Use Them In Your Workflow

## Scaling Out with Overlay Networking

docker network create --driver overlay mydrupal

docker network ls

docker service create --name psql --network mydrupal -e POSTGRES_PASSWORD=mypass postgres

docker service ls

docker service ps psql

docker container logs psql TAB COMPLETION

docker service create --name drupal --network mydrupal -p 80:80 drupal

docker service ls

watch docker service ls

docker service ps drupal

docker service inspect drupal

## Scaling Out with Routing Mesh

docker service create --name search --replicas 3 -p 9200:9200 elasticsearch:2

docker service ps search

## Assignment Answers: Create a Multi-Service Multi-Node Web App

docker node ls

docker service ls

docker network create -d overlay backend

docker network create -d overlay frontend

docker service create --name vote -p 80:80 --network frontend -- replica 2 COPY IMAGE

docker service create --name redis --network frontend --replica 1 redis:3.2

docker service create --name worker --network frontend --network backend COPY IMAGE

docker service create --name db --network backend COPY MOUNT INFO

docker service create --name result --network backend -p 5001:80 COPY INFO

docker service ls

docker service ps result

docker service ps redis

docker service ps db

docker service ps vote

docker service ps worker

cat /etc/docker/

docker service logs worker

docker service ps worker

## Swarm Stacks and Production Grade Compose

docker stack deploy -c example-voting-app-stack.yml voteapp

docker stack

docker stack ls

docker stack ps voteapp

docker container ls

docker stack services voteapp

docker stack ps voteapp

docker network ls

docker stack deploy -c example-voting-app-stack.yml voteapp

## Using Secrets in Swarm Services

docker secret create psql_usr psql_usr.txt

echo "myDBpassWORD" | docker secret create psql_pass - TAB COMPLETION

docker secret ls

docker secret inspect psql_usr

docker service create --name psql --secret psql_user --secret psql_pass -e POSTGRES_PASSWORD_FILE=/run/secrets/psql_pass -e POSTGRES_USER_FILE=/run/secrets/psql_user postgres

docker service ps psql

docker exec -it psql.1.CONTAINER NAME bash

docker logs TAB COMPLETION

docker service ps psql

docker service update --secret-rm

## Using Secrets with Swarm Stacks

vim docker-compose.yml

docker stack deploy -c docker-compose.yml mydb

docker secret ls

docker stack rm mydb

## Assignment Answers: Create A Stack with Secrets and Deploy

vim docker-compose.yml

docker stack deploy - c docker-compose.yml drupal

echo STRING |docker secret create psql-ps - VALUE

docker stack deploy -c docker-compose.yml drupal

docker stack ps drupal

# Swarm App Lifecycle

## Using Secrets With Local Docker Compose

docker node ls

docker-compose up -d

docker-compose exec psql cat /run/secrets/psql_user

docker-compose 11

pcat docker-compose.yml

## Full App Lifecycle: Dev, Build and Deploy With a Single Compose Design

docker-compose up -d

docker inspect TAB COMPLETION

docker-compose down

docker-compose -f docker-compose.yml -f docker-compose.test.yml up -d

docker inspect TAB COMPLETION

docker-compose -f docker-compose.yml -f docker-compose.prod.yml config --help

docker-compose -f docker-compose.yml -f docker-compose.prod.yml config

docker-compose -f docker-compose.yml -f docker-compose.prod.yml config > output.yml

## Service Updates: Changing Things In Flight

docker service create -p 8088:80 --name web nginx:1.13.7

docker service ls

docker service scale web=5

docker service update --image nginx:1.13.6 web

docker service update --publish-rm 8088 --publish-add 9090:80

docker service update --force web

## Healthchecks in Dockerfiles

docker container run --name p1 -d postgres

docker container ls

docker container run --name p2 -d --health-cmd="pg_isready -U postgres || exit 1" postgres

docker container ls

docker container inspect p2

docker service create --name p1 postgres

docker service create --name p2 --health-cmd="pg_isready -U postgres || exit 1" postgres

# Container Registries: Image Storage and Distribution

## Docker Hub: Digging Deeper

https://hub.docker.com

## Docker Store: What Is It For?

https://store.docker.com

## Docker Cloud: CI/CD and Server Ops

https://cloud.docker.com

https://hub.docker.com

## Understanding Docker Registry

https://github.com/docker/distribution

https://hub.docker.com/registry

## Run a Private Docker Registry

docker container run -d -p 5000:5000 --name registry registry

docker container ls

docker image ls

docker pull hello-world

docker run hello-world

docker tag hello-world 127.0.0.1:5000/hello-world

docker image ls

docker push 127.0.0.1:5000/hello-world

docker image remove hello-world

docker image remove 127.0.0.1:5000/hello-world

docker container rm admiring_stallman

docker image remove 127.0.0.1:5000/hello-world

docker image ls

docker pull 127.0.0.1:5000/hello-world:latest

docker container kill registry

docker container rm registry

docker container run -d -p 5000:5000 --name registry -v $(pwd)/registry-data:/var/lib/registry registry TAB COMPLETION

docker image ls

docker push 127.0.0.1:5000/hello-world

## Using Docker Registry With Swarm

http://play-with-docker.com

docker node ls

docker service create --name registry --publish 5000:5000 registry

docker service ps registry

docker pull hello-world

docker tag hello-world 127.0.0.1:5000/hello-world

docker push 127.0.0.1:5000/hello-world

docker pull nginx

docker tag nginx 127.0.0.1:5000/nginx

docker push 127.0.0.1:5000/nginx

docker service create --name nginx -p 80:80 --replicas 5 --detach=false 127.0.0.1:5000/nginx

docker service ps nginx


# Dockers

The repository contains my docker configurations for developement.

## Requirements

- docker
- docker-compose

## Commands (Dockerfile)

- php

```console

$ docker build -t php-app . (Command to build docker container)
$ docker run -it --name=php-app-container php-app (Command to run interactive container with name)
$ docker stop php-app-container and docker rm php-app-container (Stop and remove)
$ docker run -d -p 80:80 -v $(pwd)/app:/var/www/app --name=php-app-container php-app (Command to run volume container with name)
$ docker network create -d bridge php-app-network (Create network bridge)
$ docker run -d -v $(pwd)/.data/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secret --network=php-app-network --name=mysql mysql:5.7.24 (Run volume mysql container)
$ docker exec -it mysql bash (Enter mysql container)
$ docker run -d -p 8080:80 -v $(pwd)/app:/var/www/app --network=php-app-network --name=php-app-container php-app (Run php container with mysql container through network bridge)

```

## Commands (Docker Compose)

```console

$ docker-compose up -d --build
$ docker-compose down

```

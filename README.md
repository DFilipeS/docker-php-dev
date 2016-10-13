# PHP Development Docker Environment

This repository contains a basic configuration for a development environment for a typical AMP stack (Nginx, MySQL and PHP). Project files stored in the `public` folder are served by Nginx.

Based on [Master Zend Framework blog post](http://www.masterzendframework.com/docker-development-environment/).

## Index

* [Contents](#contents) 
* [Starting the environment](#starting-the-environment) 
* [Getting information about the containers](#getting-information-about-the-containers) 
* [SSHing into containers](#sshing-into-containers)
* [Accessing phpMyAdmin](#accessing-phpmyadmin)
* [Using a different PHP version](#using-a-different-php-version)
* [See volumes and removing them](#see-volumes-and-removing-them)
 
## Contents

* [`nginx:latest`](https://hub.docker.com/_/nginx/)
* [`php:5.6-fpm`](https://hub.docker.com/_/php/)
* [`mysql:latest`](https://hub.docker.com/_/mysql/)
* [`phpmyadmin/phpmyadmin:latest`](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)

## Starting the environment

* `$ docker-compose up`

Note: if you don't want to see the logs you can run docker-compose in daemon mode by appending the `-d` flag to the command.

After starting, you can access the server through the browser.

* `http://localhost:8080`

## Getting information about the containers

It is useful to know what containers are running, their names, expose ports, ...

* `$ docker ps`

## SSHing into containers

Sometimes it might be useful to access the actual container (for example, to import a database).

* `$ docker exec -i -t YOUR_CONTAINER_NAME /bin/bash`

## Accessing phpMyAdmin

phpMyAdmin is served by default in the port 8090.

* `http://localhost:8090`

## Using a different PHP version

By default it is used the PHP 5.6 but if you want use a diffent version just edit the version number in the `./docker/php/Dockerfile` file.

For more information about Docker images of other PHP versions check the [PHP Docker Hub](https://hub.docker.com/_/php/).

## See volumes and removing them

A new volume is created for persistently storing the database files. To list the existing volumes:

* `$ docker volume ls`

To remove a volume:

* `$ docker volume rm YOUR_VOLUME_NAME`

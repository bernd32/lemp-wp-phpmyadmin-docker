# Docker Compose LEMP Stack

This repository contains `docker-compose` configuration to start a `LEMP (Linux, Nginx, MariaDB, PHP) + wordpress + phpmyadmin` stack.

## Configuration

The Nginx configuration can be found in `nginx/default.conf`.

You can also set the following environment variables, for example in the included `.env` file:

| Key | Description |
|-----|-------------|
|APP_NAME|The name used when creating a container.|
|MARIADB_ROOT_PASSWORD|The mariaDB root password used when creating the container.|
|MARIADB_DATABASE|Name of the database used by Wordpress.|
|MARIADB_USER|Used by Wordpress.|
|MARIADB_PASSWORD|Used by Wordpress.|

## Usage

##### Clone this repository.

Clone this repository with the following command: `git clone https://github.com/bernd32/lemp-wp-phpmyadmin-docker.git`.

##### Start the server.

Start the server using the following command inside the directory you just cloned: `docker-compose up`.
Docker will now build your containers. Once the process is complete, you can access your WordPress installation at `http://localhost:8082` and your phpMyAdmin at `http://localhost:8084` and wordpress at `http://localhost:8086`.

## Entering the containers

You can use the following command to enter a container:

Where `{CONTAINER_NAME}` is one of:

`docker exec -ti {CONTAINER_NAME} /bin/bash`

* `{APP_NAME}-php`
* `{APP_NAME}-nginx`
* `{APP_NAME}-mariadb`

## Setup secure connections (optional):

If you want to set up SSL for secure connections (HTTPS), you will need to modify your Nginx configuration and possibly use Certbot for a free Let's Encrypt certificate or add your own certificate details.
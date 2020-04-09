# Introduce

sample development with docker

an php web app show 'hello world'

following [guide](https://www.youtube.com/watch?v=YFl2mCHdv24)

## Term

### Docker Hub

The place to search container image like php/mysql...

Or, post our image to repositories

## Dockerfile for PHP image explanation

First, go to page [docker hug](https://hub.docker.com)

Then, finding 'php', and choose and image that appriciate

Read instruction

### Example Create Dockerfile

```docker

FROM php:7.4-cli //--> invoke download image php
COPY src/ /var/www/html/ -> copy file from directory src
EXPOSE 80 -> listen on port 80 and ignore others

```

## Usage

### Build docker

```bash

docker build -t hello-world .

```

`-t hello-world`: naming docker is hello-world
`.`: give location of docker file

### Run docker

```bash

docker run -p 5000:80 hello-world

```

`-p 5000:80`: map port 5000 in the machine to 80 of container

### Change content and autoupdate to image

For development test, we need to auto reload source code

It means that when we update code, it will auto copy to image and we don't need to rebuild image to see new result.

Run docker with option `-v`, map a driver

```bash

docker run -p 5000:80 -v D:\Projects\docker-practical\sample.01.gettingstart\src\:/var/www/html/ hello-world

```
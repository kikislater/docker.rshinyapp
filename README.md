docker.rshinyapp
==========================

![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/rsunau/dockershiny)
![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/rsunau/dockershiny)

The repo is to dockerize a R shinyApp and make deployment easier by publish the image to DockerHub.


## R Docker Images 

The rocker-org built a few images for the rstudio and shiny server. e.g. [Docker Image rocker/shiny](https://github.com/rocker-org/shiny/blob/master/README.md)

* Image with Rstudio and Tidyverse package 

```
docker run --rm -e PASSWORD=xxx -p 8787:8787 rocker/verse
```

* Image with Rstudio and shiny server

```
docker run -d -p 3838:3838 -p 8787:8787 -e ADD=shiny -e PASSWORD=yourpasswordhere rocker/rstudio
```

* Image with the shiny server and Tidyverse package

```
docker run --rm  -p 3838:3838 rocker/shiny-verse
```


## Docker Commands
[Docker CLIs](https://docs.docker.com/engine/reference/commandline/docker/)

1. List containers

```
docker ps
```

2. Run a command in a running container 

```
docker exec -it <container name> /bin/bash
```
  
3. Run a new container

```
docker run --rm -d -p 3838:3838 rocker/shiny-verse
```

4. Stop a running container

```
docker stop <container>
```

## Run the docker

```{bash}
docker run --rm -d -p 80:3838 dockershiny

docker build -t dockershiny .

docker push rsunau/dockershiny:tagname

```

## How to use it?

1. Do Docker on your machine

1. Pull docker image from DockerHub

```
docker pull rsunau/dockershiny

docker run --rm -d -p 80:3838 dockershiny

```


## A very useful tutorial on R and Docker 
https://ropenscilabs.github.io/r-docker-tutorial/

## TODO


* fix lib for app 
* make the AutoML work in docker
* AWS to run docker

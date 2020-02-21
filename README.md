# WIP

Docker containers for Bioconductor plus Shiny Server

[![Docker Build Status](https://img.shields.io/docker/cloud/build/sudosk/bioconductor_docker_shiny.svg)](https://hub.docker.com/r/sudosk/bioconductor_docker_shiny/builds/)

This docker image can be used by any R Shiny based applications which built on top of Bioconductor packages. This image comes with Shiny Server installed on the base image of [bioconductor/bioconductor_docker:devel](https://github.com/Bioconductor/bioconductor_docker), which helps maintain the Bioconductor version and its dependencies.

## Quick start
```
docker run --rm -e PASSWORD=bioc -p 3838:3838 \
    -v /srv/shinyapps/:/srv/shiny-server/ \
    -v /srv/shinylog/:/var/log/shiny-server/ \
    sudosk/bioconductor_docker_shiny
```

## Test

```
git clone https://github.com/sk-sahu/bioconductor_docker_shiny.git
```

```
docker run --rm -e PASSWORD=bioc -p 3838:3838 \
	-v bioconductor_docker_shiny/test/:/srv/shiny-server/ 
	-v /srv/shinylog/:/var/log/shiny-server/ 
	sudosk/bioconductor_docker_shiny
```

## Acknowledgements
This is inspired by [rocker-org/shiny image](https://github.com/rocker-org/shiny) which are based on plain R. Most of the code used here are taken from this project.

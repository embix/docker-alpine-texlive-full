# embix/docker-alpine-texlive-full

this is a work in progress with the final goal to have an image to be used as tex build-env

## Build

build and tag version:

    docker build -t docker-texlive:v1 .

*Don't this, it's just a personal reminder:* build for docker hub and push:

    docker login
    docker build -t embix/texlive-full:v1 .
    docker push embix/texlive-full:v1

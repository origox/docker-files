# Dockerfile with Angular CLI

## Versions included
Node 6.11.4
Angular CLI 1.4.7

## Dockerhub
Image not yet registered

## Build Image
docker build -t origox/angular-cli .

## Run Image & map your host source folder 
### Will start up in node mode
docker run -it --rm -v "$PWD":/home/app --user $UID origox/angular-cli
### Will start in bash shell
docker run -it -p 4200:4200 --rm -v $PWD:/home/app  --user $UID origox/angular-cli:1 bash

## Usage
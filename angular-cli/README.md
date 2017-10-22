# Dockerfile with Angular CLI

## Versions included
Node 6.11.4
Angular CLI 1.4.7
tmux

## Dockerhub
Image not yet registered

## Build Image
docker build -t origox/angular-cli:2 .

## Run Image & map your host source folder and userid 
### Will start in bash shell
docker run -it -p 4200:4200 --rm -v $PWD:/home/node/appdevelopment --user $UID  origox/angular-cli:2

# MQTT Clients

MQTT Clients based on [mosquitto](https://mosquitto.org/).

## Build Image for Linux 

docker build -t origox/mqtt-client .

## Build Image for Raspberry3 & Jessie 
docker build -f Dockerfile-rpi -t origox/mqtt-client .

## Run Image

docker run -it --network=bridge --rm origox/mqtt-client

## Usage
sub -h 172.17.0.2  -t "topic1" -

pub -h 172.17.0.2 -m "msg1" -t "topic1"

## MQTT Broker
Test this broker:
docker run -it -p 1883:1883 -p 9001:9001 -v /mosquitto/config -v /mosquitto/data -v /mosquitto/log eclipse-mosquitto:1.4.12
# MQTT Broker

MQTT Broker from [mosquitto](https://mosquitto.org/).

## Build Docker Image for Raspberry

docker build -t origox/mqttbroker:1 .

## Run Image(use docker volumes for persistent data)

 docker run -it -p 8883:8883 --rm --name my-broker -v broker_data:/mqtt/data -v broker_config:/mqtt/config -v broker_log:/mqtt/log origox/mqttbroker:1

docker volume ls - verify that you can find your volumes
docker inspect broker_log - check volume meta data i.e. find mount point

## Setup TSL

### Generate Certificates

See example here: http://www.steves-internet-guide.com/mosquitto-tls/

Certificate files(ca.crt, server.crt, server.key) need to be place in config/cert

Note - ca.crt shall also be used by the clients

## Systemd

### Setup the broker to be started at boot

sudo cp mqtt-broker.service /lib/systemd/system

sudo systemctl enable mqtt-broker.service

sudo systemctl start mqtt-broker.service


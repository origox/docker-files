# MQTT Broker

MQTT Broker from [mosquitto](https://mosquitto.org/).

## Build Docker Image for Raspberry

docker build -t origox/mqttbroker:1 .

## Run Image

docker run -it -p 8883:8883 --rm --name my-broker origox/mqttbroker:1

## Setup TSL

### Generate Certificates

See example here: http://www.steves-internet-guide.com/mosquitto-tls/

### Certificate files need to be place in config/cert

### ca.crt, server.crt, server.key

### ca.crt shall be used also by the clients
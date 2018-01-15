FROM resin/rpi-raspbian:stretch

LABEL Maintainer="jfrandberg@gmail.com" \
      Description="MQTT Broker"

# Install mqtt broker
RUN apt-get update && \
    apt-get install mosquitto mosquitto-clients

RUN adduser --system --disabled-password --disabled-login mosquitto

RUN mkdir -p /mqtt/config /mqtt/data /mqtt/log
COPY config /mqtt/config
RUN chown -R mosquitto:mosquitto /mqtt
VOLUME ["/mqtt/config", "/mqtt/data", "/mqtt/log"]


EXPOSE 8883 

ADD entrypoint.sh /usr/bin/

RUN chmod 755 /usr/bin/entrypoint.sh

ENTRYPOINT ["entrypoint.sh"]
CMD ["/usr/sbin/mosquitto", "-c", "/mqtt/config/mosquitto.conf"]

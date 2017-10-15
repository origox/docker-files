FROM alpine:3.6
LABEL Maintainer="jfrandberg@gmail.com" \
      Description="Mosquitto MQTT client based on Alpine Linux"

# Install mqtt client
ENV MOSQUITTO_VERSION="1.4.12-r0"
RUN apk add --no-cache mosquitto-clients=${MOSQUITTO_VERSION}

# Setup handy shortcuts
RUN ln -s /usr/bin/mosquitto_pub /usr/local/bin/pub && \
    ln -s /usr/bin/mosquitto_sub /usr/local/bin/sub



#ARG BUILD_FROM="alpine:latest"
FROM python:3

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh makeconf.sh rs485.py /

# Install requirements for add-on
RUN apt-get update && \
    apt-get -y install jq && \
    python3 -m pip install --no-cache-dir pyserial paho-mqtt typing_extensions

WORKDIR /share

RUN chmod a+x /makeconf.sh /run.sh

CMD [ "/run.sh" ]

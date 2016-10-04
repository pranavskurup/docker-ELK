FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN useradd -d /opt/oneweb -m oneweb

RUN su oneweb

WORKDIR /opt/oneweb

RUN \
 wget https://download.elastic.co/kibana/kibana/kibana-4.3.1-linux-x64.tar.gz && \
 tar xvzf kibana-4.3.1-linux-x64.tar.gz && \
 rm -f kibana-4.3.1-linux-x64.tar.gz && \
 chown -R oneweb:oneweb kibana-4.3.1-linux-x64
 
ADD kibana.yml kibana-4.3.1-linux-x64/config/kibana.yml
 
ENTRYPOINT kibana-4.3.1-linux-x64/bin/kibana
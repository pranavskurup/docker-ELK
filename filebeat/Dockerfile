FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN useradd -d /opt/oneweb -m oneweb

RUN su oneweb

WORKDIR /opt/oneweb

RUN \
 wget https://download.elastic.co/beats/filebeat/filebeat-1.0.1-x86_64.tar.gz && \
 tar zxvf filebeat-1.0.1-x86_64.tar.gz && \
 rm -f filebeat-1.0.1-x86_64.tar.gz
 
ADD filebeat.yml filebeat-1.0.1-x86_64/filebeat.yml
ENTRYPOINT filebeat-1.0.1-x86_64/filebeat -c filebeat-1.0.1-x86_64/filebeat.yml -v
FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN useradd -d /opt/oneweb -m RUN oneweb 
RUN su oneweb
WORKDIR /opt/oneweb

RUN \
 wget https://download.elasticsearch.org/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.1.1/elasticsearch-2.1.1.tar.gz && \
 tar xvzf elasticsearch-2.1.1.tar.gz && \
 rm -f elasticsearch-2.1.1.tar.gz && \
 chown -R oneweb:oneweb elasticsearch-2.1.1

ADD elasticsearch.yml /opt/oneweb/elasticsearch-2.1.1/config/elasticsearch.yml
ENTRYPOINT elasticsearch-2.1.1/bin/elasticsearch
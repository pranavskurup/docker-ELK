FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN \
 wget https://download.elastic.co/logstash/logstash/logstash-2.1.1.tar.gz && \
 tar xvzf logstash-2.1.1.tar.gz && \
 rm -f logstash-2.1.1.tar.gz && \
 chown -R oneweb:oneweb logstash-2.1.1
 
# logstash.conf and Dockerfile are on same location
ADD logstash.conf /opt/oneweb/logstash-2.1.1/conf.d/logstash.conf
 
CMD logstash-2.1.1/bin/logstash -f logstash-2.1.1/conf.d/logstash.conf --verbose
FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget
RUN apt-get install -y openjdk-7-jre
RUN apt-get install -y openjdk-7-jdk

RUN useradd -d /opt/oneweb -m oneweb
WORKDIR /opt/oneweb
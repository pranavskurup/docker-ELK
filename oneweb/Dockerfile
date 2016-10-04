FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN useradd -d /opt/oneweb -m oneweb

RUN su oneweb

WORKDIR /opt/oneweb

RUN wget -q http://nginx.org/keys/nginx_signing.key -O- | apt-key add -
RUN echo deb http://ppa.launchpad.net/nginx/stable/ubuntu wily main && /etc/apt/sources.list
RUN echo deb-src http://ppa.launchpad.net/nginx/stable/ubuntu wily main && /etc/apt/sources.list
 
RUN apt-get update
RUN apt-get -y install nginx pwgen python-setuptools curl git unzip vim rsyslog
RUN service rsyslog start
 
RUN chown -R www-data:www-data /var/lib/nginx
RUN rm -v /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/
 
WORKDIR /etc/nginx
 
ENTRYPOINT service nginx start
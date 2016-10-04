FROM  java:8u102-jdk
MAINTAINER Pranav S Kurup

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y wget

RUN apt-get -y install nginx pwgen python-setuptools curl git unzip vim rsyslog
RUN service rsyslog start
 
RUN chown -R www-data:www-data /var/lib/nginx
RUN rm -v /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/
 
WORKDIR /etc/nginx
 
ENTRYPOINT service nginx start
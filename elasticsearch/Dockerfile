#FROM docker.elastic.co/elasticsearch/elasticsearch:6.1.2

# Set the base image to Ubuntu
FROM ubuntu:14.04

# File Author / Maintainer
MAINTAINER Kevin Murillo Fernández

# INSTALL JAVA

#RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" > /etc/apt/sources.list.d/webupd8team-java.list
#RUN echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu precise main" >> /etc/apt/sources.list.d/webupd8team-java.list
#RUN apt-get update
#RUN apt-get -y install software-properties-common
#RUN add-apt-repository ppa:webupd8team/java
#RUN apt-get -y --force-yes install git curl oracle-java7-installer


#RUN apt-get update && \
#    apt-get install -y software-properties-common && \
#    add-apt-repository ppa:webupd8team/java -y && \
#    apt-get update && \
#    echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
#    apt-get install -y --force-yes oracle-java8-installer && \
#    apt-get clean

RUN \
  apt-get update && \
  apt-get install -y software-properties-common && \
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y oracle-java8-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk8-installer

# Define working directory.
WORKDIR /data

# Define commonly used JAVA_HOME variable
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

# INSTALL ELASTICSEARCH

RUN apt-get install -y curl

RUN curl -L -O https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/tar/elasticsearch/2.4.6/elasticsearch-2.4.6.tar.gz

RUN tar -xvf elasticsearch-2.4.6.tar.gz

RUN ./elasticsearch-2.4.6/bin/elasticsearch
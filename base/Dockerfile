FROM ubuntu:12.04
MAINTAINER Rafal Wojdyla "ravwojdyla@gmail.com"

# Install java:
RUN \
  echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  apt-get update && \
  apt-get install -y python-software-properties && \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y oracle-java7-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk7-installer

ENV JAVA_HOME /usr/lib/jvm/java-7-oracle

# Add Hortonworks repo:
ADD hdp.list /etc/apt/sources.list.d/hdp.list
RUN gpg --keyserver pgp.mit.edu --recv-keys B9733A7A07513CAD && gpg -a --export 07513CAD | apt-key add -

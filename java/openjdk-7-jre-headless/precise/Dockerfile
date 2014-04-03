FROM ubuntu:precise

RUN echo "deb http://au.archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y language-pack-en && locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8
RUN apt-get install -y openjdk-7-jre-headless
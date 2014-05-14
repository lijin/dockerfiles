FROM ubuntu:precise

RUN apt-get update

RUN apt-get install -y language-pack-en && locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# No need for recommended packages:
RUN apt-get install -y --no-install-recommends openjdk-7-jre-headless openjdk-7-jdk

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64
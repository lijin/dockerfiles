FROM ubuntu:precise

RUN echo "deb http://au.archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y language-pack-en && locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# No need for recommended packages:
#  krb5-locales icedtea-7-jre-cacao icedtea-7-jre-jamvm
RUN apt-get install -y --no-install-recommends openjdk-7-jre-headless
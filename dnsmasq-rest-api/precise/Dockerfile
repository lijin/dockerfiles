# dnsmasq-rest-api:precise
# Installs https://github.com/bpaquet/dnsmasq-rest-api
# Based on https://github.com/amp/lab/docker-scripts/dnsmasq-precise
#
FROM ubuntu:precise

RUN echo "deb http://au.archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update

RUN apt-get install -y curl dnsutils git php5 psmisc

RUN apt-get install -y dnsmasq
RUN echo "user=root" > /etc/dnsmasq.conf
RUN echo "resolv-file=/etc/resolv.dnsmasq.conf" >> /etc/dnsmasq.conf
RUN echo "conf-dir=/etc/dnsmasq.d"  >> /etc/dnsmasq.conf

RUN echo "nameserver 8.8.8.8" >> /etc/resolv.dnsmasq.conf
RUN echo "nameserver 8.8.4.4" >> /etc/resolv.dnsmasq.conf

RUN curl https://raw.githubusercontent.com/bpaquet/dnsmasq-rest-api/master/install.sh | sudo bash

ADD files /root/dnsmasq_files

CMD ["/root/dnsmasq_files/default_cmd"]
dnsmasq-rest-api
============

Runs dnsmasq on ubuntu 12.04 with support for [REST API](https://github.com/bpaquet/dnsmasq-rest-api).

Usage
-----

```bash
$ sudo docker run -p 80:80 -p 53:53 -p 53:53/udp -d lijin/dnsmasq-rest-api:precise
```
or
```bash
$ IP=$(ip -o -4 addr list docker0 | perl -n -e 'if (m{inet\s([\d\.]+)\/\d+\s}xms) { print $1 }')
$ sudo docker run -p 80:80 -p $IP:53:53 -p $IP:53:53/udp -d lijin/dnsmasq-rest-api:precise
```
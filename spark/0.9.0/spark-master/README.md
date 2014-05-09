spark-master
============

Image for Spark Master.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

Set `DNS_SERVER` to the IP address of the dnsmasq server.
Set `MASTER_HOSTNAME`, e.g. "master".
Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname\`".
Set `PUBLIC_IP`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-ipv4\`".

```shell
$ DNS_SERVER=
$ MASTER_HOSTNAME=master
$ SPARK_PUBLIC_DNS=
$ PUBLIC_IP=
$ sudo docker run -d -h $MASTER_HOSTNAME\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "PUBLIC_IP=$PUBLIC_IP"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -p 8080:8080 -p 7077:7077 lijin/spark-master:0.9.0
```
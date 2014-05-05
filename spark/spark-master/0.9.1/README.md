spark-master
============

Image for Spark Master.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

* Set `DNS_SERVER` to the IP address of the dnsmasq server.
* Set `MASTER_FQDN`, e.g. "master.spark.cluster".
* Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname`".

```Shell
$ DNS_SERVER=
$ MASTER_FQDN=
$ SPARK_PUBLIC_DNS=
$ sudo docker run -d -h $MASTER_FQDN\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -p 8080:8080 -p 7077:7077 lijin/spark-master:0.9.0
```
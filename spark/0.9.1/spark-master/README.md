spark-master
============

Image for Spark Master.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

* Set `DNS_SERVER` to the IP address of the dnsmasq server.
* Set `MASTER_FQDN`, e.g. "master.spark.cluster".
* Set `SPARK_MASTER_PORT`, e.g. "7077".
* Set `SPARK_MASTER_WEBUI_PORT`, e.g. "8080".
* Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname`".

```bash
$ DNS_SERVER=
$ MASTER_FQDN=
$ SPARK_MASTER_PORT=
$ SPARK_MASTER_WEBUI_PORT=
$ SPARK_PUBLIC_DNS=
$ sudo docker run -d -h $MASTER_FQDN\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "SPARK_MASTER_IP=$MASTER_FQDN"\
  -e "SPARK_MASTER_PORT=$SPARK_MASTER_PORT"\
  -e "SPARK_MASTER_WEBUI_PORT=$SPARK_MASTER_WEBUI_PORT"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -p $SPARK_MASTER_PORT:$SPARK_MASTER_PORT\
  -p $SPARK_MASTER_WEBUI_PORT:$SPARK_MASTER_WEBUI_PORT\
  lijin/spark-master:0.9.1
```
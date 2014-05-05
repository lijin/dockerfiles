spark-worker
============

Image for Spark Worker.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

Start [spark-master](../../spark-master)

* Set `DNS_SERVER` to the IP address of the dnsmasq server.
* Set `MASTER_FQDN`, e.g. "master.spark.cluster".
* Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname`".
* Set `SPARK_WORKER_PORT`, e.g. "56800".
* Set `SPARK_WORKER_WEBUI_PORT`, e.g. "8081".

```shell
$ DNS_SERVER=
$ MASTER_FQDN=
$ SPARK_PUBLIC_DNS=
$ SPARK_WORKER_PORT=
$ SPARK_WORKER_WEBUI_PORT=
$ sudo docker run -d\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "SPARK_MASTER_IP=$MASTER_FQDN"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -e "SPARK_WORKER_PORT=$SPARK_WORKER_PORT"\
  -e "SPARK_WORKER_WEBUI_PORT=$SPARK_WORKER_WEBUI_PORT"\
  -p $SPARK_WORKER_PORT:$SPARK_WORKER_PORT\
  -p $SPARK_WORKER_WEBUI_PORT:$SPARK_WORKER_WEBUI_PORT\
  lijin/spark-worker:0.9.0
```
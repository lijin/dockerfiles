spark-worker
============

Image for Spark Worker.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

Start [spark-master](../spark-master)

* Set `DNS_SERVER` to the IP address of the dnsmasq server.
* Set `WORKER_FQDN`, e.g. "worker1.spark.cluster".
* Set `MASTER_FQDN`, e.g. "master.spark.cluster".
* Set `SPARK_MASTER_PORT`, e.g. "7077"
* Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname`".
* Set `SPARK_WORKER_PORT`, e.g. "56800".
* Set `SPARK_WORKER_WEBUI_PORT`, e.g. "8081".

```bash
$ DNS_SERVER=
$ WORKER_FQDN=
$ MASTER_FQDN=
$ SPARK_MASTER_PORT=
$ SPARK_PUBLIC_DNS=
$ SPARK_WORKER_PORT=
$ SPARK_WORKER_WEBUI_PORT=
$ CID=$(sudo docker run -d -h $WORKER_FQDN\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "SPARK_MASTER_IP=$MASTER_FQDN"\
  -e "SPARK_MASTER_PORT=$SPARK_MASTER_PORT"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -e "SPARK_WORKER_PORT=$SPARK_WORKER_PORT"\
  -e "SPARK_WORKER_WEBUI_PORT=$SPARK_WORKER_WEBUI_PORT"\
  -p $SPARK_WORKER_PORT:$SPARK_WORKER_PORT\
  -p $SPARK_WORKER_WEBUI_PORT:$SPARK_WORKER_WEBUI_PORT\
  lijin/spark-worker:0.9.1)
$ WORKER_IP=`sudo docker inspect --format='{{.NetworkSettings.IPAddress}}' $CID`
$ curl -X POST http://$DNS_SERVER/dnsmasq-rest-api/zones/spark/$IP/$WORKER_FQDN
$ curl -X POST http://$DNS_SERVER/dnsmasq-rest-api/reload
```

To stop the worker, run the following commands:

```bash
$ sudo docker stop $CID
$ curl -X DELETE http://$DNS_SERVER/dnsmasq-rest-api/zones/spark/$WORKER_IP/$WORKER_FQDN
$ curl -X POST http://$DNS_SERVER/dnsmasq-rest-api/reload
```

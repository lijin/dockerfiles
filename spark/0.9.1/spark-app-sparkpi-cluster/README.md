spark-app-sparkpi-cluster
============

Image for standalone Spark application SparkPi in cluster deploy mode.

Usage
-----

Start [dnsmasq-rest-api](https://index.docker.io/u/lijin/dnsmasq-rest-api/) server.

Start [spark-master](../../spark-master)

Start [spark-worker](../../spark-worker)

* Set `DNS_SERVER` to the IP address of the dnsmasq server.
* Set `MASTER_FQDN`, e.g. "master.spark.cluster".
* Set `SPARK_MASTER_PORT`, e.g. "7077".
* Set `SPARK_PUBLIC_DNS`, e.g. "\`curl http://169.254.169.254/latest/meta-data/public-hostname`".
* Set `SPARK_UI_PORT` for `SPARK_JAVA_OPTS`, e.g. "4040", which becomes "-Dspark.ui.port=4040".
* Set `AWS_ACCESS_KEY_ID`
* Set `AWS_SECRET_ACCESS_KEY`

Note: no port-forwarding for `spark.ui.port` will be set up.

```bash
$ DNS_SERVER=
$ MASTER_FQDN=
$ SPARK_MASTER_PORT=
$ SPARK_PUBLIC_DNS=
$ SPARK_UI_PORT=4040
$ SPARK_JAVA_OPTS=-Dspark.ui.port=$SPARK_UI_PORT
$ sudo docker run -d\
  --dns $DNS_SERVER -e "DNS_SERVER=$DNS_SERVER"\
  -e "SPARK_MASTER_IP=$MASTER_FQDN"\
  -e "SPARK_MASTER_PORT=$SPARK_MASTER_PORT"\
  -e "SPARK_PUBLIC_DNS=$SPARK_PUBLIC_DNS"\
  -e "SPARK_JAVA_OPTS=$SPARK_JAVA_OPTS"\
  -e "AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID"\
  -e "AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY"\
  lijin/spark-app-sparkpi-cluster:0.9.1
```
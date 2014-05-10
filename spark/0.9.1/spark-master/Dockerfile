# Spark master
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
FROM lijin/spark-base:0.9.1

# Override the following
# ENV SPARK_PUBLIC_DNS

# Override and bind the master to the specified ports
# ENV SPARK_MASTER_PORT 7077
# ENV SPARK_MASTER_WEBUI_PORT 8080

# Optional
# ENV SPARK_LOCAL_IP # Required if hostname resolves to public IP
# ENV SPARK_JAVA_OPTS

ADD files /root/spark_master_files

CMD ["/root/spark_master_files/default_cmd"]

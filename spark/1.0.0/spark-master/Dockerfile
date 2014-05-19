# Spark master
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
FROM lijin/spark-base:1.0.0

# ENV SPARK_MASTER_OPTS

# Override the following
# ENV SPARK_PUBLIC_DNS

# ENV SPARK_MASTER_PORT

# Override and bind the master to the specified ports
# ENV SPARK_MASTER_WEBUI_PORT

# Optional
# ENV SPARK_LOCAL_IP # Required if hostname resolves to public IP

ADD files /root/spark_master_files

CMD ["/root/spark_master_files/default_cmd"]

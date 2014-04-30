# Spark master
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
FROM lijin/spark-base:0.9.1

ENV SPARK_MASTER_PORT 7077
ENV SPARK_MASTER_WEBUI_PORT 8080

# Expose TCP ports 7077 8080
EXPOSE 7077 8080

# Override the following
# ENV SPARK_PUBLIC_DNS

# Optional
# ENV SPARK_JAVA_OPTS

# Not used
# ENV SPARK_LOCAL_IP

ADD files /root/spark_master_files

CMD ["/root/spark_master_files/default_cmd"]

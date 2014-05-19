# Spark worker
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
#
FROM lijin/spark-base:1.0.0

# ENV SPARK_WORKER_CORES
# ENV SPARK_WORKER_MEMORY
# ENV SPARK_WORKER_INSTANCES
# ENV SPARK_WORKER_DIR
# ENV SPARK_WORKER_OPTS

# Override the following based on values set in Spark master
# ENV SPARK_MASTER_IP
# ENV SPARK_MASTER_PORT

# Override the following
# ENV SPARK_PUBLIC_DNS

# Override and bind the worker to the specified ports
# ENV SPARK_WORKER_PORT
# ENV SPARK_WORKER_WEBUI_PORT

# Optional
# ENV SPARK_LOCAL_IP # Required if hostname resolves to public IP

ADD files /root/spark_worker_files

CMD ["/root/spark_worker_files/default_cmd"]

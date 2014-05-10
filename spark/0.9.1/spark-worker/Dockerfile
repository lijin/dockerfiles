# Spark worker
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
#
FROM lijin/spark-base:0.9.1

# ENV SPARK_WORKER_CORES
# ENV SPARK_WORKER_MEMORY
# ENV SPARK_WORKER_INSTANCES
# ENV SPARK_WORKER_DIR

# Override the following
# ENV SPARK_MASTER_IP
# ENV SPARK_MASTER_PORT
# ENV SPARK_PUBLIC_DNS

# Override and bind the worker to the specified ports
# ENV SPARK_WORKER_PORT
# ENV SPARK_WORKER_WEBUI_PORT

# Optional
# ENV SPARK_LOCAL_IP # Required if hostname resolves to public IP
# ENV SPARK_JAVA_OPTS

ADD files /root/spark_worker_files

CMD ["/root/spark_worker_files/default_cmd"]

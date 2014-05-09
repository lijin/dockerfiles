# Spark worker
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
# Usage: sudo docker run -P lijin/spark-worker:0.9.0
#
FROM lijin/spark-base:0.9.0

# ENV SPARK_WORKER_CORES
# ENV SPARK_WORKER_MEMORY
# ENV SPARK_WORKER_INSTANCES
# ENV SPARK_WORKER_DIR

# See spark-master
ENV SPARK_MASTER_PORT 7077
ENV SPARK_MASTER_WEBUI_PORT 8080

# Override the following
# ENV SPARK_MASTER_IP
# ENV SPARK_PUBLIC_DNS

# Override and bind the worker to a specific port
# ENV SPARK_WORKER_PORT
# ENV SPARK_WORKER_WEBUI_PORT

# Optional
# ENV SPARK_LOCAL_IP
# ENV SPARK_JAVA_OPTS

ADD files /root/spark_worker_files

CMD ["/root/spark_worker_files/default_cmd"]

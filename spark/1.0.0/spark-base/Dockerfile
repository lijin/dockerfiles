# Spark base
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
FROM lijin/openjdk-7-jre-headless:precise

#ENV SCALA_VERSION 2.10.4
ENV SPARK_VERSION 1.0.0
# hadoop1, cdh4, hadoop2
ENV SPARK_HDP_VERSION hadoop2
ENV SPARK_HOME /opt/spark-$SPARK_VERSION

RUN apt-get install -y wget

# Install Spark
RUN wget -q http://d3kbcqa49mib13.cloudfront.net/spark-$SPARK_VERSION-bin-$SPARK_HDP_VERSION.tgz -O - | tar -xvz -C /opt && ln -s /opt/spark-$SPARK_VERSION-bin-$SPARK_HDP_VERSION /opt/spark-$SPARK_VERSION

# Add Spark config files and configure script
ADD files /root/spark_files
RUN cp /root/spark_files/conf/* /opt/spark-$SPARK_VERSION/conf/

# Setup sshd
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:password' |chpasswd

# Override if required (e.g. using net=host)
ENV SSHD_PORT 22

CMD    /usr/sbin/sshd -p $SSHD_PORT -D

# Spark base
# Modified based on amplab/docker-scripts <github.com/amplab/docker-scripts>
#
FROM lijin/openjdk-7-jre-headless:precise

ENV SCALA_VERSION 2.10.3
ENV SPARK_VERSION 1.0.0-snapshot
# hadoop1, cdh4, hadoop2
ENV SPARK_BIN_VERSION hadoop1
#ENV SCALA_HOME /opt/scala-$SCALA_VERSION
ENV SPARK_HOME /opt/spark-$SPARK_VERSION

RUN apt-get install -y wget

# Install Scala
#RUN (cd / && wget -q http://www.scala-lang.org/files/archive/scala-$SCALA_VERSION.tgz && gunzip < scala-$SCALA_VERSION.tgz)|(cd /opt && tar -xvf - && rm /scala-$SCALA_VERSION.tgz)

# Install Spark
Add /spark/dist /opt/spark-1.0.0-snapshot

# Add Spark config files and configure script
ADD files /root/spark_files
RUN cd / && cp /root/spark_files/conf/* /opt/spark-$SPARK_VERSION/conf/

# Setup sshd
RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:password' |chpasswd

# Override if required (e.g. using net=host)
ENV SSHD_PORT 22

CMD    /usr/sbin/sshd -p $SSHD_PORT -D

FROM java:7-jre
MAINTAINER Xusheng Gong <gongxsh00@163.com>
ENV REFRESHED_AT 2016-01-24
RUN curl  http://10.77.3.123/zookeeper-3.4.10.tar.gz -o zookeeper-3.4.10.tar.gz \
    && tar -xzf zookeeper-3.4.10.tar.gz -C /opt \
    && mv /opt/zookeeper-3.4.10 /opt/zookeeper \
    && cp /opt/zookeeper/conf/zoo_sample.cfg /opt/zookeeper/conf/zoo.cfg \
    && mkdir -p /tmp/zookeeper

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64 

EXPOSE 2181 2888 3888

WORKDIR /opt/zookeeper

VOLUME ["/opt/zookeeper/conf", "/tmp/zookeeper"]

ENTRYPOINT ["/opt/zookeeper/bin/zkServer.sh"]
CMD ["start-foreground"]

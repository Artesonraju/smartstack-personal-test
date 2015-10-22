FROM artesonraju/oracle-java7

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

RUN wget -q -O - http://apache.mirrors.pair.com/zookeeper/zookeeper-3.4.6/zookeeper-3.4.6.tar.gz | tar -xzf - -C /opt && \
    mv /opt/zookeeper-3.4.6 /opt/zookeeper && \
    rm /opt/zookeeper/conf/log4j.properties && \
    mkdir -p /tmp/zookeeper && \
    mkdir -p /opt/zookeeper/logs

# client, quorum and leader election ports
EXPOSE 2181 2888 3888 9998

WORKDIR /opt/zookeeper

ADD ./zkServer.sh /opt/zookeeper/zkServer.sh
RUN mv -f /opt/zookeeper/zkServer.sh /opt/zookeeper/bin/zkServer.sh

ENV JMXPORT 9998
ENV JMXAUTH false
ENV JMXSSL false
ENV JMXLOG4J false

# volumes for configuration, logs, data
VOLUME ["/opt/zookeeper/conf", "/opt/zookeeper/logs", "/tmp/zookeeper"]

ENTRYPOINT ["/opt/zookeeper/bin/zkServer.sh"]
CMD ["start-foreground"]

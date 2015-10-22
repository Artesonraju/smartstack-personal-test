FROM artesonraju/oracle-java7

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

RUN wget -q -O - http://mirrors.ircam.fr/pub/apache/kafka/0.8.1.1/kafka_2.10-0.8.1.1.tgz |  tar -xzf - -C /opt && \
    mv /opt/kafka_2.10-0.8.1.1 /opt/kafka && \
    mkdir -p /tmp/kafka-logs && \
    mkdir -p /opt/kafka/logs

# configuration, logs and data volume
VOLUME ["/opt/kafka/config", /opt/kafka/logs, "/tmp/kafka-logs"]

WORKDIR /opt/kafka

ENV JMX_PORT 9999

# server and jmx ports
EXPOSE 9092 9999

# working on local only

CMD cp -f config/server.properties config/server_adapted.properties && \
    cat config/server.properties | \
      sed "/advertised\.host\.name/c\advertised\.host\.name=$(awk 'NR==1 {print $1}' /etc/hosts)" \
      > config/server_adapted.properties && \
    bin/kafka-server-start.sh config/server_adapted.properties
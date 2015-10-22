FROM artesonraju/clojure

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

VOLUME ["/conf"]

WORKDIR /src

RUN git clone https://github.com/Artesonraju/kafka-to-riemann && \
  cd kafka-to-riemann && \
  lein uberjar && \
  cp ./target/kafka-to-riemann-0.1.0-SNAPSHOT-standalone.jar /src/kafka-to-riemann-clj.jar && \
  cd .. && \
  rm -r ./kafka-to-riemann

CMD java -jar -Dlog4j.configuration=file:"/config/log4j.properties" riemann-jmx-clj.jar /conf/config.yml
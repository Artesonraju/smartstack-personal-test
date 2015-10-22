FROM artesonraju/clojure

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

VOLUME ["/conf"]

WORKDIR /src

RUN git clone https://github.com/Artesonraju/riemann-jmx && \
  cd riemann-jmx && \
  git checkout retry-and-wait-on-ioexception &&\
  lein uberjar && \
  cp ./target/riemann-jmx-clj-0.1.0-SNAPSHOT-standalone.jar /src/riemann-jmx-clj.jar && \
  cd .. && \
  rm -r ./riemann-jmx

CMD java -jar riemann-jmx-clj.jar $(ls /conf/*.yml)
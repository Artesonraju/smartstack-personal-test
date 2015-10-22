FROM artesonraju/oracle-java7

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

RUN apt-get update && \
    apt-get install -y --no-install-recommends bzip2 && \
    rm -rf /var/lib/apt/lists/* && \  
    wget -q -O - https://aphyr.com/riemann/riemann-0.2.9.tar.bz2 | tar xvfj - -C /opt && \
    mv /opt/riemann-0.2.9 /opt/riemann && \
    mkdir -p /conf

# configuration
VOLUME [/conf]

WORKDIR /opt/riemann

# server ports for tcp and websockets
EXPOSE 5555 5556

CMD bin/riemann /conf/riemann.config
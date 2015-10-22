FROM artesonraju/oracle-java7

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

ADD ./lein /usr/bin/lein

RUN chmod a+x /usr/bin/lein
RUN apt-get update && apt-get install -y --no-install-recommends git \
	&& rm -rf /var/lib/apt/lists/* \
    && lein
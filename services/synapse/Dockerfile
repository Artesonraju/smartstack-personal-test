FROM artesonraju/ruby

ADD ./Gemfile /src/Gemfile

WORKDIR /src

RUN apt-get update && apt-get install -y --no-install-recommends \
    haproxy \ 
    rsyslog\
	&& rm -rf /var/lib/apt/lists/* \
    && gem install bundler \
    && bundle install --path /var/lib/gems/2.1.0/ --binstubs /usr/local/bin/

# configuration, logs and data volume
VOLUME ["/conf", "/etc/haproxy/haproxy.cfg"]

EXPOSE 1936

CMD service haproxy start && synapse -c /conf/synapse.conf.yml
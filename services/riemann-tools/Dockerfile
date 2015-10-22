FROM artesonraju/ruby

ADD ./Gemfile /src/Gemfile

WORKDIR /src

RUN gem install bundler \
    && bundle install --path /var/lib/gems/2.1.0/ --binstubs /usr/local/bin/ \
    && mkdir /conf

VOLUME [/conf, /var/run/docker.sock]

CMD riemann-tools /conf/config.json

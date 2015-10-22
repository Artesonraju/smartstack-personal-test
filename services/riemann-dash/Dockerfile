FROM artesonraju/ruby

RUN gem install riemann-dash --no-doc

WORKDIR /conf

# configuration
VOLUME [/conf]

EXPOSE 4567

CMD riemann-dash
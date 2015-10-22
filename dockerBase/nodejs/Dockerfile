FROM debian:8.0

MAINTAINER  Etienne Molto "molto.etienne@gmail.com"

# Install curl and nodejs
RUN apt-get update && apt-get install -y --no-install-recommends \
		ca-certificates \
		curl \
		wget \
        locales \
    && curl -sL https://deb.nodesource.com/setup | bash - \
    && apt-get install -y nodejs \
	&& rm -rf /var/lib/apt/lists/*

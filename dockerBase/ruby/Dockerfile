FROM debian:8.0

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    ruby \
    ruby-dev \
    zlib1g-dev \
	&& rm -rf /var/lib/apt/lists/*
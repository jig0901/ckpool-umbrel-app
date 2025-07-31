FROM debian:bullseye

# Install dependencies
RUN apt-get update && apt-get install -y \
  build-essential \
  git \
  autoconf \
  libcurl4-openssl-dev \
  libjansson-dev \
  libssl-dev \
  libgmp-dev \
  automake \
  pkg-config

# Clone CKPool
RUN git clone https://bitbucket.org/ckolivas/ckpool.git /ckpool

# Build CKPool
WORKDIR /ckpool
RUN ./autogen.sh && ./configure && make

# Default command to run CKPool (adjust args/config as needed)
CMD ["/src/ckpool", "-c", "ckpool.conf", "-k", "-q"]

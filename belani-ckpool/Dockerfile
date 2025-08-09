FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

# Install build dependencies
RUN apt-get update && \
    apt-get install -y \
    git \
    build-essential \
    libcurl4-openssl-dev \
    libjansson-dev \
    uthash-dev \
    automake \
    libtool \
    autoconf \
    pkg-config && \
    apt-get clean

# Clone ckpool
RUN git clone https://bitbucket.org/ckolivas/ckpool.git /ckpool

# Build ckpool
WORKDIR /ckpool
RUN ./autogen.sh && ./configure CFLAGS="-O2" && make \
  && cp /ckpool/src/ckpool /usr/local/bin/ckpool

# Copy your custom config (optional: mount this instead)
COPY ckpool.conf /ckpool/ckpool.conf

# Expose default stratum port
EXPOSE 3333

# Run ckpool with config
CMD ["./ckpool", "-c", "ckpool.conf", "-k", "-q"]
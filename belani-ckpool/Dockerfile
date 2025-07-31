FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y git build-essential libcurl4-openssl-dev libjansson-dev uthash-dev automake libtool autoconf pkg-config && \
    apt-get clean

# Clone CKPool
RUN git clone https://bitbucket.org/ckolivas/ckpool.git /ckpool

# Build CKPool
WORKDIR /ckpool
# Patch global_ckp declaration
RUN ./autogen.sh && ./configure CFLAGS="-O2" && make

# Default command to run CKPool (adjust args/config as needed)
CMD ["/src/ckpool", "-c", "ckpool.conf", "-k", "-q"]

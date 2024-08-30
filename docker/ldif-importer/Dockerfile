FROM debian:bookworm AS builder

# Install dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    openssl \
    libssl-dev \
    zlib1g-dev \
    wget

# Download and build curl
RUN wget https://curl.se/download/curl-8.9.1.tar.gz && \
    tar -xzf curl-8.9.1.tar.gz && \
    cd curl-8.9.1 && \
    ./configure --with-openssl --disable-shared && \
    make

FROM nathluu/ds-empty:7.3.1

USER 0

COPY --from=builder /curl-8.9.1/src/curl /usr/local/bin/curl

RUN apt-get update -y && apt-get install -y curl

USER 11111

COPY --chown=forgerock:root start.sh /opt/opendj
COPY --chown=forgerock:root ds-passwords.sh /opt/opendj

ENTRYPOINT /opt/opendj/start.sh

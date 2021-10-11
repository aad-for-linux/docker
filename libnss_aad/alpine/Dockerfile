FROM alpine:3.14

RUN apk update && \
    apk add \
        automake \
        cmake \
        curl \
        git \
        indent \
        jansson-dev \
        libsds-dev \
        libsodium-dev \
        libtool \
        quilt

WORKDIR /usr/src/libnss_aad
COPY . /usr/src/libnss_aad

RUN make && make install


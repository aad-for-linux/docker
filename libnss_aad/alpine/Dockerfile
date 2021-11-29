FROM alpine:3.14

RUN echo 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories && \
    apk update && apk add \
      automake \
      cmake \
      curl-dev \
      gcc \
      git \
      indent \
      jansson-dev \
      libsds-dev \
      libsodium-dev \
      libtool \
      make \
      quilt


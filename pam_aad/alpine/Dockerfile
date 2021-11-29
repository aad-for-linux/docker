FROM alpine:3.14

RUN echo 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories && \
    apk update && apk add \
      autoconf \
      automake \
      curl-dev \
      gcc \
      git \
      indent \
      jansson-dev \
      libsds-dev \
      libtool \
      linux-pam-dev \
      make \
      musl-dev \
      quilt


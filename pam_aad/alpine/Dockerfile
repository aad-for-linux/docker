FROM alpine:3.14

RUN echo 'http://dl-cdn.alpinelinux.org/alpine/edge/testing' >> /etc/apk/repositories && \
    apk update && apk add \
      automake \
      curl \
      git \
      indent \
      jansson-dev \
      libsds-dev \
      linux-pam-dev \
      quilt


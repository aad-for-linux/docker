FROM ubuntu:20.04
ARG VERSION
ARG DEBVER

RUN apt update && apt install -y \
        software-properties-common && \
    add-apt-repository -y ppa:lramage/sds

RUN apt update && apt install -y \
        automake \
        build-essential \
        curl \
        debhelper \
        devscripts \
        git \
        indent \
        libcurl4-openssl-dev \
        libjansson-dev \
        libjwt-dev \
        libpam0g-dev \
        libsds-dev \
        libssl-dev \
        libtool \
        pkg-config \
        quilt \
        uuid-dev


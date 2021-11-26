FROM ubuntu:20.04
ARG VERSION
ARG DEBVER

RUN apt update && apt install -y \
        software-properties-common && \
    add-apt-repository -y ppa:lramage/sds

RUN apt update && apt install -y \
        automake \
        autopoint \
        build-essential \
        cmake \
        curl \
        debhelper \
        devscripts \
        git \
        indent \
        libcurl4-openssl-dev \
        libjansson-dev \
        libjwt-dev \
        libsds-dev \
        libsodium-dev \
        libssl-dev \
        libtool \
        libcrypt-dev \
        pkg-config \
        quilt


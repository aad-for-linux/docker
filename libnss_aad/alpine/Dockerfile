FROM alpine:3.14

RUN >> /etc/apk/repositories && \
    apk update && apk add \
        automake \
        cmake \
        curl \
        git \
        indent \
        jansson-dev \
        libsodium-dev \
        libtool \
        quilt \
        libsds

WORKDIR /usr/src/libnss_aad
COPY . /usr/src/libnss_aad
RUN tar cvzf "../libnss-aad_${VERSION}.orig.tar.gz" --exclude='.git*' . && \
    make -us -uc -i'.git' && \

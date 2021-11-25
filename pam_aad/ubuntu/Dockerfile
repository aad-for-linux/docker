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

RUN git clone https://github.com/aad-for-linux/pam_aad.git /usr/src/pam_aad

WORKDIR /usr/src/pam_aad
RUN tar cvzf "../pam-aad_${VERSION}.orig.tar.gz" --exclude='.git*' . && \
    debuild -us -uc -d -i'(.*)' && \
    dpkg -i "../libpam-aad_${VERSION}-${DEBVER}_amd64.deb"


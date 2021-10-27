FROM alpine:3.14
ARG VERSION
ARG DEBVER

RUN echo "deb http://http.us.debian.org/debian bullseye main" \
        >> /etc/apk/repositories && \
    apk update && apk add -y \
        automake \
        curl \
        git \
        indent \
        libjansson-dev \
        libpam0g-dev \
        quilt \

# missing packages \
build-essential \
debhelper \
devscripts \
libcurl4-openssl-dev \
libjwt-dev \
libssl-dev \
libtool \
pkg-config \
uuid-dev
        
ENV SDSMIRROR="https://gitlab.com/oxr463/sds/-/jobs/210491217/artifacts/raw" \
    SDSVERSION="2.0.0" SDSDEBVERSION="2.0.0-1"
WORKDIR /tmp
RUN curl -LO "${SDSMIRROR}/libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    curl -LO "${SDSMIRROR}/libsds-dev_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds-dev_${SDSDEBVERSION}_amd64.deb"

WORKDIR /usr/src/pam_aad
COPY . /usr/src/pam_aad
RUN tar cvzf "../pam-aad_${VERSION}.orig.tar.gz" --exclude='.git*' . && \
    debuild -us -uc -d -i'(.*)' && \
    dpkg -i "../libpam-aad_${VERSION}-${DEBVER}_amd64.deb"
 

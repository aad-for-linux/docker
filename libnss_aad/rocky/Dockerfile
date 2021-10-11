FROM rockylinux/rockylinux:8.4

RUN echo "deb http://http.us.debian.org/debian bullseye main" \
        >> /etc/dnf/dnf.conf && \
    dnf update && dnf install -y \
        automake \
        cmake \
        curl \
        git \
        indent \
        libcurl-devel \
        jansson-devel \
        libtool \
        libxcrypt-devel \
        quilt
        
ENV SDSMIRROR="https://gitlab.com/oxr463/sds/-/jobs/210491217/artifacts/raw" \
    SDSVERSION="2.0.0" SDSDEBVERSION="2.0.0-1"
WORKDIR /tmp
RUN curl -LO "${SDSMIRROR}/libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    curl -LO "${SDSMIRROR}/libsds-dev_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds-dev_${SDSDEBVERSION}_amd64.deb"

WORKDIR /usr/src/libnss_aad
COPY . /usr/src/libnss_aad

RUN make && make install


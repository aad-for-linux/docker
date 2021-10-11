FROM rockylinux/rockylinux:8.4

RUN >> /etc/dnf/dnf.conf && \
    dnf update && dnf install -y \
        automake \
        curl \
        git \
        indent \
        libjansson-dev \
        libtool \
        quilt \

ENV SDSMIRROR="https://gitlab.com/oxr463/sds/-/jobs/210491217/artifacts/raw" \
    SDSVERSION="2.0.0" SDSDEBVERSION="2.0.0-1"
WORKDIR /tmp
RUN curl -LO "${SDSMIRROR}/libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    curl -LO "${SDSMIRROR}/libsds-dev_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds${SDSVERSION}_${SDSDEBVERSION}_amd64.deb" && \
    dpkg -i "libsds-dev_${SDSDEBVERSION}_amd64.deb"

WORKDIR /usr/src/pam_aad
COPY . /usr/src/pam_aad

ENV PAMROC="/lib64/security" \
    NSS_PATH="$"{NSS_PATH}:/usr/local/lib:/usr/local/lib64"    
RUN ./bootstrap.sh && \
    ./configure --with-pam-dir="${PAMROC}" && \
    make && make install

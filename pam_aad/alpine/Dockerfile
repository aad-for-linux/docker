FROM alpine:3.14

RUN >> /etc/apk/repositories && \
    apk update && apk add -y \
        automake \
        curl \
        git \
        indent \
        libjansson-dev \
        libpam0g-dev \
        quilt \
        libsds

WORKDIR /usr/src/pam_aad
COPY . /usr/src/pam_aad
RUN tar cvzf "../pam-aad_${VERSION}.orig.tar.gz" --exclude='.git*' . && \
    make -us -uc -d -i'(.*)' &&
 

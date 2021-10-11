FROM aad-for-linux/pam_aad:alpine

RUN apk update && \
    apk add \
        liblz4-dev \
        liblzo2-dev \
        openvpn \
        wget

WORKDIR /usr/src/openvpn_auth_aad
COPY . /usr/src/openvpn_auth_aad

RUN make && make install


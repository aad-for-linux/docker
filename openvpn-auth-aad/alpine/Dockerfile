FROM aad-for-linux/pam_aad:alpine

RUN apk update -qq && apk add -y \
      liblz4-dev \
      liblzo2-dev \
      openvpn \
      wget

WORKDIR /usr/src/openvpn-auth-aad
COPY . /usr/src/openvpn-auth-aad
RUN useradd -m dev -s /bin/bash && \
    chown -R dev:dev /usr/src/openvpn-auth-aad

RUN tar cvzf "../openvpn-auth-aad_${VERSION}.orig.tar.gz" --exclude='.git*' . && \
    make -us -uc -d -i'(.*)' && \

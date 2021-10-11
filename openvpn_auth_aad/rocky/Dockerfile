FROM aad-for-linux/pam_aad:rocky

RUN dnf update -qq && dnf install -y \
      liblz4-dev \
      liblzo2-dev \
      openvpn \
      wget

WORKDIR /usr/src/openvpn_auth_aad
COPY . /usr/src/openvpn_auth_aad

RUN ./bootstrap.sh && make && make install


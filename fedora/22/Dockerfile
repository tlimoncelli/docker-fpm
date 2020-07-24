FROM fedora:22

RUN set -x \
    && dnf install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && dnf clean all \
    && mkdir /tmp/src

WORKDIR /tmp/src/

CMD /usr/local/bin/fpm

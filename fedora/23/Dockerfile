FROM fedora:23

RUN set -x \
    && dnf install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && dnf clean all \
    && mkdir /tmp/src

WORKDIR /tmp/src/

CMD /usr/local/bin/fpm

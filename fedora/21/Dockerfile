FROM fedora:21

RUN set -x \
    && yum install -y ruby-devel gcc make rpmdevtools \
    && gem install fpm \
    && yum clean all \
    && mkdir /tmp/src

WORKDIR /tmp/src/

CMD /usr/local/bin/fpm

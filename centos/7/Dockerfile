FROM centos:7

RUN set -x \
    && yum install -y ruby-devel rubygems gcc make rpmdevtools \
    && gem install fpm \
    && yum clean all \
    && mkdir /tmp/src

WORKDIR /tmp/src/

CMD /usr/local/bin/fpm

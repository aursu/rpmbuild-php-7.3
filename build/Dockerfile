ARG centos=7.9.2009
FROM aursu/rpmbuild:${centos}-build

USER root

RUN yum -y install \
        libc-client \
        pcre2-devel \
    && yum clean all && rm -rf /var/cache/yum /var/lib/rpm/__db*

COPY system/etc/yum.repos.d/bintray-custom.repo /etc/yum.repos.d/bintray-custom.repo

RUN yum -y --enablerepo=bintray-custom --enablerepo=bintray-php73custom install \
        php-cli \
        php-common \
        php-devel \
        php-process \
        php-xml \
    && yum clean all && rm -rf /var/cache/yum /var/lib/rpm/__db*
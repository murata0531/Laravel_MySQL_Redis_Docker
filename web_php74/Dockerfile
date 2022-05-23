FROM centos:centos7

# timezone
RUN rm -f /etc/localtime \
    && cp -p /usr/share/zoneinfo/Japan /etc/localtime

# php7.4
    RUN yum -y update \
    && yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm \
    && yum -y install https://rpms.remirepo.net/enterprise/remi-release-7.rpm \
    && yum -y install yum-utils \
    && yum-config-manager --disable 'remi-php*' && yum-config-manager --enable remi-php74 \
    && yum remove php* \
    && yum -y install --enablerepo=remi-php74 apache php php-devel php-json php-mbstring php-mysqlnd php-xml redis MariaDB-server \
    && php --version

# apache
RUN yum install -y httpd httpd-devel \
    && rm -rf /var/cache/yum/* \
    && yum clean all \
    && mkdir -p /app/ENV /AccessLog.local
COPY ./setup/httpd/app.conf /etc/httpd/conf.d/app.conf

# composer
RUN cd /tmp && curl -sS https://getcomposer.org/installer | php \
    && mv ./composer.phar /usr/bin/composer

CMD ["httpd", "-D", "FOREGROUND"]
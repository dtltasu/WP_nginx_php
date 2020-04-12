FROM centos:8

RUN dnf install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm && \
    dnf install -y https://rpms.remirepo.net/enterprise/remi-release-8.rpm
    
RUN dnf -y install dnf-utils && \
    dnf -y module enable php:remi-7.4

RUN dnf install -y \
    php \
    php-fpm \
    php-bcmath \
    php-cli \
    php-common \
    php-curl \
    php-fpm \
    php-intl \
    php-mbstring \
    php-mcrypt \
    php-mysqlnd \
    php-opcache \
    php-pdo \
    php-pecl-zip \
    php-soap \
    php-phar \
    php-process \
    php-pgsql \
    php-redis \
    php-xml \
    openssl \
    curl \
    git

#RUN useradd -M -d /opt/app nginx

RUN mkdir -p /run/php-fpm && \
    chown nginx:nginx /run/php-fpm

RUN mkdir -p /var/lib/php/session && \
    chown nginx:nginx /var/lib/php/session

COPY php-fpm.conf /etc/php-fpm.conf
COPY www.conf /etc/php-fpm.d/www.conf
COPY php.ini /etc/php/ini

EXPOSE 9000

CMD ["php-fpm", "--nodaemonize"]


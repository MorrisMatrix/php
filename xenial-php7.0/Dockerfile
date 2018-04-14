FROM ubuntu:xenial

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update \
    && apt-get dist-upgrade -y 

# Install PHP
RUN apt-get install -y \
    php7.0 \
    zip unzip php7.0-zip \
    php7.0-xml \
    php7.0-fpm \
    php7.0-curl \
    php7.0-mcrypt \
    php7.0-mbstring \
    php-memcached \
    php7.0-mysql \
    php7.0-int \
    php-pear \
    php7.0-dev \
    iputils-ping \
    apt-transport-https \
    git \
    curl \
    wget \
    vim

# Cleanup and remove unnecessary packages
RUN apt-get autoclean \
    && apt-get autoremove

ADD run.sh /
RUN chmod +x /run.sh
CMD ["/run.sh"]
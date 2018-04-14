FROM ubuntu:bionic

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

RUN apt-get update \
    && apt-get dist-upgrade -y
    
# Install PHP
RUN apt-get install -y \
    php7.2 \
    zip unzip php7.2-zip \
    php7.2-xml \
    php7.2-fpm \
    php7.2-curl \
    php7.2-mbstring \
    php-memcached \
    php7.2-mysql \
    php-pear \
    php7.2-dev \
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
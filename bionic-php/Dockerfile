FROM ubuntu:bionic

RUN echo 'debconf debconf/frontend select Noninteractive' | debconf-set-selections

# Install/Upgrade/Autoclean
RUN apt-get update \
    && apt-get dist-upgrade -y \
    && apt-get install -y

# Install PHP
RUN apt-get install -y \
    php7.2 \
    zip unzip php7.2-zip \
    php7.2-xml \
    git \
    php7.2-fpm \
    curl \
    php7.2-curl \
    apt-transport-https \
    php7.2-mbstring \
    wget \
    php-memcached \
    vim \
    php7.2-mysql \
    php-pear \
    php7.2-dev 

# Cleanup and remove unnecessary packages
RUN apt-get autoclean \
    && apt-get autoremove

ADD run.sh /
RUN chmod +x /run.sh
CMD ["/run.sh"]
FROM php:7.1-fpm

RUN apt-get update \
        && echo 'deb http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list \
        && echo 'deb-src http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list \
        && apt-get install -y wget \
        && wget https://www.dotdeb.org/dotdeb.gpg \
        && apt-key add dotdeb.gpg \
        && apt-get update \
        && apt-get install -y  \
            php7.0-mysql \
            libfreetype6-dev \
            libjpeg62-turbo-dev \
            libmcrypt-dev \
            libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) mysqli pdo pdo_mysql gd

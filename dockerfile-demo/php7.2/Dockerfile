FROM php:7.2-fpm

LABEL maintainer="Siqing Mu <siqingmu@gmail.com>"

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    procps \
    emacs \
    telnet \
    iputils-ping \
    curl \
    wget

RUN pecl install \
    xdebug-2.8.1 \
    redis-5.1.1

RUN docker-php-ext-enable \
    xdebug \
    redis

RUN docker-php-ext-install -j$(nproc) \
    mysqli \
    pdo \
    zip \
    && docker-php-ext-configure gd \
    --with-freetype-dir=/usr/include/ \
    --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

COPY php.ini /usr/local/etc/php/

WORKDIR /usr/local/src


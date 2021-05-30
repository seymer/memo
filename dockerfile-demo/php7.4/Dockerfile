FROM php:7.4-fpm

LABEL maintainer="Siqing Mu <siqingmu@gmail.com>"

# COPY sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    librdkafka-dev \
    libzip-dev \
    procps \
    emacs \
    telnet \
    iputils-ping \
    curl \
    wget

RUN docker-php-ext-install -j$(nproc) \
    mysqli \
    opcache \
    pdo \
    pdo_mysql \
    zip \
    && docker-php-ext-configure gd \
    --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

RUN pecl install \
    xdebug-3.0.4 \
    redis-5.3.4 \
    mongodb-1.9.1 \
    rdkafka-5.0.0

RUN docker-php-ext-enable \
    opcache \
    xdebug \
    redis \
    mongodb \
    rdkafka

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

WORKDIR /usr/local/src


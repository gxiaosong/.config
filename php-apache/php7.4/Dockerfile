FROM php:74-apache

RUN apt-get update && apt-get install -y \
    curl \
    libicu-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    git \
    cron \
    zip \
    unzip

COPY ./swoole_loader_74_nts.so /usr/local/lib/php/extensions/no-debug-non-zts-20190902
RUN echo 'extension=swoole_loader_74_nts.so' >> /usr/local/etc/php/php.ini

RUN pecl install swoole

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli && \
    docker-php-ext-install gd && docker-php-ext-enable gd && \
    docker-php-ext-enable swoole
    

FROM php:8.1-apache

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


RUN pecl install swoole
RUN pecl install swoole_loader

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli && \
    docker-php-ext-install gd && docker-php-ext-enable gd && \
    docker-php-ext-enable swoole && docker-php-ext-enable swoole_loader
    

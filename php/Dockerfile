FROM php:8.0.12-apache

COPY ./php.ini /usr/local/etc/php
COPY ./apache2.conf /etc/apache2/conf-enabled
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN apt-get update
RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libmcrypt-dev vim libzip-dev zlib1g-dev
RUN docker-php-ext-install mysqli pdo_mysql gd zip
RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

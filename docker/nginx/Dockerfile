FROM php:8.0-fpm

# Composer install
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

# install Node.js
COPY --from=node:16.13 /usr/local/bin /usr/local/bin
COPY --from=node:16.13 /usr/local/lib /usr/local/lib

RUN apt-get -y update; apt-get install ca-certificates
RUN apt-get -y install git zip unzip vim
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install bcmath

WORKDIR /var/www/html
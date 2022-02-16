FROM php:8.1.2-fpm-alpine

RUN apk add libpq-dev openssl zip unzip
RUN docker-php-ext-install -j$(nproc) bcmath ctype fileinfo pdo pdo_pgsql opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
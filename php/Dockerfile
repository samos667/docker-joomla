ARG PHP_VERSION=""
FROM php:${PHP_VERSION:+${PHP_VERSION}-}fpm-alpine

RUN apk update; \
    apk upgrade;

RUN mkdir -p /var/www/html/joomla

RUN docker-php-ext-install mysqli
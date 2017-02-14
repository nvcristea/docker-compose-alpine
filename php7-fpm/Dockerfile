FROM php:7.1-fpm-alpine

MAINTAINER Nicolae V. Cristea <coder@cristea.bid>

# Environments
ENV TIMEZONE        Europe/Bucharest

RUN apk add --update --no-cache tzdata \
    && cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
    && echo "${TIMEZONE}" > /etc/timezone

RUN docker-php-ext-configure pdo \
    && pecl install xdebug \
    && docker-php-ext-install pdo_mysql

COPY xdebug.ini $PHP_INI_DIR/conf.d/

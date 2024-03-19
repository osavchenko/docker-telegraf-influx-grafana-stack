FROM php:8.3-fpm-alpine

RUN apk update && apk add --no-cache \
        autoconf \
        g++ \
        icu-dev \
        make \
        mysql-client \
    && pecl install mongodb \
    && docker-php-ext-install \
        intl \
        pdo_mysql \
    && docker-php-ext-enable \
        intl \
        pdo_mysql \
        mongodb

COPY --from=composer/composer:2-bin /composer /usr/bin/composer

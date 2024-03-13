FROM php:8.3-fpm-alpine

RUN apk update && apk add --no-cache \
        icu-dev \
        mysql-client \
    && docker-php-ext-install \
        intl \
        pdo_mysql \
    && docker-php-ext-enable \
        intl \
        pdo_mysql

COPY --from=composer/composer:2-bin /composer /usr/bin/composer

FROM php:8.1-fpm

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        git zip unzip ssh mc cron htop \
        libicu-dev

RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer \
    composer global require "fxp/composer-asset-plugin:^1.3.1"

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN docker-php-ext-install pdo pdo_mysql


RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony

RUN docker-php-ext-configure intl \
    && docker-php-ext-install intl
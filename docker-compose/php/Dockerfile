FROM php:8.0-fpm
COPY ./php.ini /usr/local/etc/php/
RUN apt-get update \
   && apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev libonig-dev zip unzip \
   && docker-php-ext-install pdo_mysql mysqli gd iconv exif

# Composer install
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

# node install
COPY --from=node:12.14 /usr/local/bin /usr/local/bin
COPY --from=node:12.14 /usr/local/lib /usr/local/lib

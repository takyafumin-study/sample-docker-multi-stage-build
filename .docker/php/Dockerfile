FROM php:8.3.2-fpm-alpine3.19 AS builder

COPY --from=composer /usr/bin/composer /usr/local/bin/
COPY --from=mlocati/php-extension-installer:2.2 /usr/bin/install-php-extensions /usr/local/bin/

RUN set -eux \
 && apk update \
 && apk --no-cache add \
    git \
    unzip \
    libzip-dev \
 && install-php-extensions bcmath exif opcache zip

WORKDIR /var/www/src

FROM builder as dev

RUN set -eux \
  && apk --no-cache add \
    autoconf \
    gcc \
    g++ \
    make \
  && install-php-extensions xdebug

FROM builder as prod

COPY ./src /var/www/src
RUN composer install

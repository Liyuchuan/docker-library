FROM php:7.4.33-cli-alpine3.16

COPY --from=composer/composer:2.2-bin /composer /usr/bin/composer

RUN apk add --no-cache \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd \
    && apk del --no-cache freetype-dev libjpeg-turbo-dev libpng-dev
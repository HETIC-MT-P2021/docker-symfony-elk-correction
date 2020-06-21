FROM php:7.4-fpm-alpine3.10

RUN apk add --update \
    make \
    curl \
    libsodium \
    libsodium-dev \
    freetype \
    libpng \
    libjpeg-turbo \
    freetype-dev \
    libpng-dev \
    libjpeg-turbo-dev \
    zlib-dev \
    icu-dev \
    libxml2-dev \
    libzip-dev \
    oniguruma-dev \
    g++

RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-configure intl
RUN docker-php-ext-configure zip
RUN docker-php-ext-install gd \
    intl \
    pdo \
    mbstring \
    zip \
    pdo_mysql

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/download/1.10.5/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

RUN composer global require hirak/prestissimo

ADD symfony.ini /usr/local/etc/php/conf.d/
ADD symfony.pool.conf /usr/local/etc/php-fpm.d/

CMD ["php-fpm", "-F"]

WORKDIR /var/www/symfony
EXPOSE 9001

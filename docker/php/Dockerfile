FROM php:7.2-fpm-alpine

RUN set -eux \
    && apk --no-cache add \
    vim \
    postgresql-dev \
    libzip-dev \
    icu-libs \
    bash \
    autoconf \
    g++ \
    gcc \
    make \
    icu-dev \
    libtool \
    openssh \
    git

# Install composer
RUN curl https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

RUN pecl install -f xdebug

RUN docker-php-ext-install \
    intl \
    pdo_pgsql \
    zip \
    sockets

RUN docker-php-ext-configure zip --with-libzip \
        && docker-php-ext-enable xdebug

WORKDIR /var/www

CMD ["php-fpm", "-F"]
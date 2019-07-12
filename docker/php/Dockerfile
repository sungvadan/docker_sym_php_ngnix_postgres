FROM php:7.2-fpm-alpine

RUN set -eux \
    && apk --no-cache add \
    vim \
    git

# Install composer
RUN curl https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer


WORKDIR /var/www

CMD ["php-fpm", "-F"]
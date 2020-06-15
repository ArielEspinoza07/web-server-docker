
ARG PHP_VERSION
ARG BASE_IMAGE_TAG_PREFIX=latest

FROM php:${PHP_VERSION}}-fpm

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

#Check php version

RUN set -xe; php -v | head -n 1 | grep -q "PHP ${PHP_VERSION}."

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
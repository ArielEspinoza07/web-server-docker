
ARG PHP_VERSION

FROM php:${PHP_VERSION}-fpm


# RUN set -eux; \
#     apt-get update; \
#     apt-get upgrade -y; \
#     apt-get install -y --no-install-recommends \
#     curl \
#     libmemcached-dev \
#     libz-dev \
#     libpq-dev \
#     libjpeg-dev \
#     libpng-dev \
#     libfreetype6-dev \
#     libssl-dev \
#     libmcrypt-dev; \
#     # cleanup
#     rm -rf /var/lib/apt/lists/*

# RUN apt-get install -y php-soap && \ 
#     docker-php-ext-install soap
    

# RUN apt-get install -y php-curl \ 
#     php-gd2 \ 
#     php-mbstring \ 
#     php-mysqli \ 
#     php-pdo_mysql \ 
#     php-soap \
#     docker-php-ext-install soap

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

#Check php version

RUN set -xe; php -v | head -n 1 | grep -q "PHP ${PHP_VERSION}."

WORKDIR /var/www

CMD ["php-fpm"]

EXPOSE 9000
ARG PHP_VERSION=7.4

FROM php:${PHP_VERSION}-fpm

RUN apt-get update && apt-get install -y

# Install modules
RUN apt-get install -y --no-install-recommends \
        git \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        libpq-dev \
        nano \
    && docker-php-ext-install \
        zip \
        intl \
        pdo \
        mysqli \
        pdo_mysql \
        opcache

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

# Install Symfony
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

# Set the default directory inside the container
WORKDIR /var/www/html

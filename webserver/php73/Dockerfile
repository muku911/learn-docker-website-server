FROM php:7.3.33-fpm-bullseye

COPY ./kumadev-config.ini /usr/local/etc/php/conf.d/kumadev-config.ini

RUN apt-get update && \
    apt-get install -y \
    libcurl4-openssl-dev \
    libicu-dev \
    libjpeg-dev \
    libpng-dev \
    libxml2-dev \
    libzip-dev \
    unzip \
    && docker-php-ext-install \
    bcmath \
    exif \
    gd \
    intl \
    mysqli \
    # opcache \
    pdo \
    pdo_mysql \
    soap \
    sockets \
    zip \
    && pecl install \
    redis\
    && docker-php-ext-enable \
    redis.so\
    && rm -rf /var/lib/apt/lists/*

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

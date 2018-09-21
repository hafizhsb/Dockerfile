FROM php:7.2-apache

RUN a2enmod rewrite \
 && DEBIAN_FRONTEND=noninteractive apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
 && apt-get install -y libmcrypt-dev \
 && rm -rf /var/lib/apt/lists/* \
 && pecl install mcrypt-1.0.1 \
 && docker-php-ext-enable mcrypt \
 && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
 && docker-php-ext-install -j$(nproc) gd

 COPY . /var/www/html/
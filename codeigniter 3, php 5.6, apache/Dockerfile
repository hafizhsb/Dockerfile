FROM php:5.6-apache

RUN apt-get update && apt-get install -y libpq-dev && docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN a2enmod rewrite

COPY . /var/www/html/

EXPOSE 80

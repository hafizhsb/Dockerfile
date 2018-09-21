FROM php:7.2

RUN apt-get update -y && apt-get install -y openssl zip unzip git
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install -j$(nproc) iconv mysqli pdo pdo_mysql mbstring 

WORKDIR /app
COPY . /app

CMD CD /app
RUN composer install
RUN composer update
CMD php artisan serve --host=0.0.0.0 --port=80
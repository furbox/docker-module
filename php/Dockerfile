FROM php:7.4-apache

COPY . /var/www/html

RUN apt-get update -y && apt-get install -y libonig-dev libzip-dev libz-dev libpng-dev  openssl zip unzip curl

RUN apt-get update -y && apt-get install - zlib1g-dev

RUN docker-php-ext-install gd zip pdo mbstring mysqli pdo_mysql
RUN docker-php-ext-enable mysqli

RUN a2enmod headers expires rewrite

WORKDIR /var/www/html
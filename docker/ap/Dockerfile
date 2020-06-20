FROM php:7.4-fpm
COPY php.ini /usr/local/etc/php/

RUN apt-get update \
  && apt-get install -y zlib1g-dev libzip-dev mariadb-client vim git unzip\
  && docker-php-ext-install zip pdo_mysql 

RUN cd /usr/bin && curl -s http://getcomposer.org/installer | php && ln -s /usr/bin/composer.phar /usr/bin/composer
RUN composer global require "laravel/installer"

RUN curl -SL https://deb.nodesource.com/setup_14.x | bash
RUN apt-get install -y nodejs && \
  npm install -g npm@latest && \
  npm install -g @vue/cli

WORKDIR /var/www

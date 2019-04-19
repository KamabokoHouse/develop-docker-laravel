FROM php:fpm

ENV COMPOSER_ALLOW_SUPERUSER 1
ENV COMPOSER_HOME /composer
ENV PATH $PATH:/composer/vendor/bin

RUN apt-get update -y
RUN apt-get install -y git unzip
RUN apt-get install -y libzip-dev
RUN apt-get install -y libpq-dev
RUN apt-get install -y zlib1g-dev
RUN docker-php-ext-install zip
RUN docker-php-ext-install pdo_mysql pdo_pgsql
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

RUN composer global require "laravel/installer" 

RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs
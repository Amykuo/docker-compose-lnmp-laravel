FROM php:7.4.2-fpm

RUN apt-get update \
  #&& apt-get upgrade -y \
  #&& apt-get install -y libcurl4-openssl-dev \
  && apt-get install -y libzip-dev zip unzip \
  && docker-php-ext-install pdo_mysql mysqli zip \
  && apt-get install -y vim \
  && apt-get install -y libmemcached-dev zlib1g-dev libonig-dev \
  && pecl install memcached \
  && docker-php-ext-enable memcached \
  && pecl install redis \
  && docker-php-ext-enable redis \
  && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
  && composer global require laravel/installer 

ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8
ENV PATH="$PATH:/root/.composer/vendor/bin"

WORKDIR /var/www/html
EXPOSE 9000

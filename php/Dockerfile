
FROM php:8.2-fpm-alpine

RUN docker-php-ext-install \
    bcmath \
    pdo_mysql \
    opcache

COPY opcache.ini /usr/local/etc/php/conf.d/opcache.ini

RUN apk add --no-cache \
    npm \
    linux-headers

RUN apk add --no-cache $PHPIZE_DEPS \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
RUN alias composer='/usr/bin/composer'

COPY ../flashcards /var/www
WORKDIR /var/www

RUN /usr/bin/composer update

RUN php artisan migrate 
RUN php artisan db:seed --class InitialSeeder

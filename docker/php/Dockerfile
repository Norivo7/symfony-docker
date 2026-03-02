FROM php:8.5-fpm

RUN apt update && apt install -y \
    	git unzip curl nano \
    	libicu-dev libzip-dev; \
	docker-php-ext-install intl opcache zip pdo; \
	pecl install apcu; \
	docker-php-ext-enable apcu; \
	docker-php-ext-install zip

COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer

WORKDIR /var/www/app

COPY docker/php/conf.d/*.ini /usr/local/etc/php/conf.d/

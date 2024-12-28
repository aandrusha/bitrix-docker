FROM php:8.3-apache
RUN apt-get update && apt-get install -y \
        libmemcached-dev zlib1g-dev libssl-dev \
		libfreetype-dev libjpeg62-turbo-dev libpng-dev \
        libxml2-dev libzip-dev \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install mysqli pdo_mysql \
    && docker-php-ext-install opcache \
    && docker-php-ext-install zip \
    && docker-php-ext-install xml \
    && pecl install memcache \
    && docker-php-ext-enable memcache \
    && docker-php-ext-enable mysqli \
    && a2enmod rewrite
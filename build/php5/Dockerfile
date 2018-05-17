FROM php:5.6-apache
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
        libsqlite3-dev \
    && docker-php-ext-install -j$(nproc) exif gd iconv json mcrypt mysqli opcache pdo pdo_mysql pdo_sqlite zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

# Enable Apache mod_rewrite
RUN a2enmod rewrite
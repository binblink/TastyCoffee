FROM php:fpm

RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev wget git zip vim bash libxml2-dev libpng-dev \
    && docker-php-ext-install pdo pdo_mysql intl

#zip
RUN apt-get install -y \
        libzip-dev \
        zip \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip



RUN apt-get update && \
    apt-get install -y \
    libfreetype6-dev \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libgmp-dev \
    libldap2-dev \
    sqlite3 \
    libsqlite3-dev && \
    docker-php-ext-install gd pdo pdo_mysql pdo_sqlite zip  pcntl sysvmsg exif

# Install composer

# Install Composer globally
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && php composer-setup.php && php -r "unlink('composer-setup.php');" && mv composer.phar /usr/local/bin/composer

WORKDIR /var/www

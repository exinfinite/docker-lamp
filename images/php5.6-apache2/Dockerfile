FROM php:5.6.39-apache
ENV TZ=Asia/Taipei
#COPY php/php.ini /usr/local/etc/php/
COPY server.crt /etc/apache2/ssl/server.crt
COPY server.key /etc/apache2/ssl/server.key
COPY dev.conf /etc/apache2/sites-enabled/dev.conf
RUN docker-php-ext-install pdo_mysql mysql mysqli mbstring exif \
    && a2enmod rewrite \
    && a2enmod headers \
    && a2enmod expires \
    && a2enmod ssl
RUN pecl install apcu-4.0.11 \
    && docker-php-ext-enable apcu
RUN docker-php-ext-enable opcache
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
		libzip-dev \
        zip \
		libtidy-dev \
	&& docker-php-ext-configure zip --with-libzip \
	&& docker-php-ext-install zip \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
	&& docker-php-ext-install fileinfo \
	&& docker-php-ext-install tidy \
    && docker-php-ext-enable tidy
FROM php:5.6-fpm
MAINTAINER Amine HADDAD <zatamine@gmail.com>

# Install modules
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd \
    && docker-php-ext-configure mysql --with-mysql=mysqlnd \
    # && docker-php-ext-configure mysqli --with-mysqli=mysqlnd \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    # && docker-php-ext-configure mbstring --enable-mbstring \
    
    && docker-php-ext-install mbstring mysql pdo_mysql \
    && docker-php-ext-install gd \
    

&& apt-get clean \
&& rm -rf /var/lib/apt/lists/*
CMD ["php-fpm"]

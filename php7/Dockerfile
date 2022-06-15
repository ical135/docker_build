FROM php:7.2.11-apache

# PDO mysql
RUN docker-php-ext-install mysqli pdo_mysql

# Install Postgre PDO
RUN apt-get update \
    && apt-get install -y git \
    && apt-get install -y libpq-dev \
    && apt-get install -y libc-client-dev libkrb5-dev \
    && apt-get install -y sendmail libpng-dev \
    && docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql pgsql


RUN docker-php-ext-install mbstring
RUN docker-php-ext-install gd
RUN docker-php-ext-install bcmath

# Imap
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
        && docker-php-ext-install imap \
        && docker-php-ext-enable imap

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# rewrite for .htaccess 
RUN a2enmod rewrite
RUN service apache2 restart

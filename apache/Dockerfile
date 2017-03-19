FROM php:5.6.30-apache

#RUN a2enmod rewrite
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN usermod -u 1000 www-data

COPY vhost.conf /etc/apache2/sites-enabled/000-default.conf
#COPY php.ini /usr/local/etc/php
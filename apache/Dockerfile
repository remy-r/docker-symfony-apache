FROM eboraas/apache-php

RUN a2enmod rewrite

RUN usermod -u 1000 www-data

COPY vhost.conf /etc/apache2/sites-enabled/000-default.conf
COPY php.ini /usr/local/etc/php
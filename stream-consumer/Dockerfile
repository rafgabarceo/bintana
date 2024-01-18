FROM php:8.2-apache
COPY ./install-composer.sh /install-composer.sh
RUN apt-get update && apt-get upgrade -y
RUN apt-get install libzip-dev -y
RUN pecl install mongodb 
RUN mv $PHP_INI_DIR/php.ini-production $PHP_INI_DIR/php.ini
RUN echo "extension=mongodb" >> /$PHP_INI_DIR/php.ini
RUN docker-php-ext-install zip
RUN /bin/bash -c "/install-composer.sh"
RUN composer require mongodb/mongodb

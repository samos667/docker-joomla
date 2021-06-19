ARG PHP_VERSION=""
FROM php:${PHP_VERSION:+${PHP_VERSION}-}apache

RUN apt update; \
    apt upgrade -y; \
    apt install -y unzip;

RUN docker-php-ext-install mysqli

ADD https://downloads.joomla.org/cms/joomla3/3-9-26/Joomla_3-9-26-Stable-Full_Package.zip /tmp/joomla.zip
RUN mkdir -p /var/www/html/joomla
RUN unzip /tmp/joomla.zip -d /var/www/html/joomla
RUN chown -R www-data:www-data /var/www/html/joomla
RUN chmod -R 755 /var/www/html/joomla
RUN a2dissite 000-default.conf
RUN a2enmod rewrite
COPY joomla.conf /etc/apache2/sites-available/joomla.conf
RUN a2ensite joomla.conf
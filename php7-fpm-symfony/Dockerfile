# See https://github.com/docker-library/php/blob/4677ca134fe48d20c820a19becb99198824d78e3/7.0/fpm/Dockerfile
FROM php:7.0-fpm

MAINTAINER Duong Tien Dat <mrduong.92@gmail.com>

RUN apt-get update && apt-get install -y \
	nginx 

# Install Symfony
RUN mkdir -p /usr/local/bin \
	&& curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony \ 
 	&& chmod a+x /usr/local/bin/symfony

RUN cd /var/www/ \
	&& symfony new vpc2.0 2.8

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Type docker-php-ext-install to see available extensions
RUN docker-php-ext-install pdo pdo_mysql

RUN echo 'alias sf="php app/console"' >> ~/.bashrc
RUN echo 'alias sf3="php bin/console"' >> ~/.bashrc

WORKDIR /var/www/vpc2.0

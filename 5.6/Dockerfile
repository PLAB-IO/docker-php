FROM php:5.6-fpm

#Install essential stuff
#git are required by composer
#vim is usefull for debug container in interactive shell
RUN apt-get update && apt-get install -y \
	git \
	vim \
	telnet \ 
	bzip2 \
	libbz2-dev \
	libfreetype6-dev \ 
	libjpeg62-turbo-dev \ 
	libmcrypt-dev \ 
	libpng12-dev \ 
	libghc-postgresql-libpq-dev \ 
	&& docker-php-ext-install mcrypt mbstring bz2 zip \ 
	&& docker-php-ext-configure gd -with-freetype-dir=/usr/include/ -with-jpeg-dir=/usr/include/ \ 
	&& docker-php-ext-configure pgsql -with-pgsql=/usr/include/postgresql/ \ 
	&& docker-php-ext-install gd pgsql

#module need to be install too =>> reflection sockets spl standard xml

#Install composer
RUN curl -sS https://getcomposer.org/installer | php \
	&& mv composer.phar /usr/bin/composer

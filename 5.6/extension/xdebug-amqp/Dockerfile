FROM plab/docker-php:5.6-fpm-xdebug

RUN apt-get update && apt-get install -y \
    librabbitmq-dev

RUN curl -sS https://pecl.php.net/get/amqp-1.6.0beta3.tgz -o amqp-1.6.0beta3.tgz \
    && mkdir -p /usr/src/php/amqp \
    && tar -xof amqp-1.6.0beta3.tgz -C /usr/src/php/amqp --strip-components=1 \
    && rm amqp-1.6.0beta3.tgz \
    && cd /usr/src/php/amqp \
    && phpize \
    && ./configure \
    && make \
    && make install \
    && echo "extension=amqp.so" > /usr/local/etc/php/conf.d/ext-amqp.ini

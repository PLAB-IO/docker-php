FROM plab/docker-php:5.6-fpm

#Install Xdebug
RUN curl -sS https://xdebug.org/files/xdebug-2.3.2.tgz -o xdebug-2.3.2.tgz \
    && mkdir -p /usr/src/php/xdebug \
    && tar -xof xdebug-2.3.2.tgz -C /usr/src/php/xdebug --strip-components=1 \
    && rm xdebug-2.3.2.tgz \
    && cd /usr/src/php/xdebug \
    && phpize \
    && ./configure \
    && make \
    && make install \
    && find /usr/local/lib/php/extensions -type f -name xdebug.so | xargs -I X echo "zend_extension = X" >> /usr/local/etc/php/php.ini

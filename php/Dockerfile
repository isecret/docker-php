FROM php:7.2-fpm-mysqli

RUN apt-get update -y
RUN apt-get install wget
RUN docker-php-ext-install pdo_mysql mysqli \
    && wget -c http://pecl.php.net/get/yaf-3.0.7.tgz \
        && tar -xvzf yaf-3.0.7.tgz \
        && cd yaf-3.0.7 \
        && phpize \
        && ./configure \
        && make \
        && make install \
        && cd .. \
        && rm -rf yaf-3.0.7* \
        && echo "extension=yaf.so" >> /usr/local/etc/php/conf.d/yaf.ini \
    && wget -c http://pecl.php.net/get/redis-4.1.1.tgz \
        && tar -xvzf redis-4.1.1.tgz \
        && cd redis-4.1.1 \
        && phpize \
        && ./configure \
        && make \
        && make install \
        && cd .. \
        && rm -rf redis-4.1.1.tgz* \
        && echo "extension=redis.so" >> /usr/local/etc/php/conf.d/redis.ini

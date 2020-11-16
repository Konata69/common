FROM php:7.4-fpm-buster
LABEL maintainer="shaykinspicewolf@gmail.com"

COPY . /var/www/html
WORKDIR /var/www/html

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Mysql pdo drivers
RUN docker-php-ext-install pdo pdo_mysql

# Install xdebug
RUN pecl install xdebug && docker-php-ext-enable xdebug

# Xdebug config
RUN echo "xdebug.remote_enable=true" | tee -a /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=0" | tee -a /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.idekey=PHPSTORM" | tee -a /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.profiler_enable=0" | tee -a /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.max_nesting_level=700" | tee -a /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_host=172.17.0.1" | tee -a /usr/local/etc/php/conf.d/xdebug.ini
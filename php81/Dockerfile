FROM php:8.1-fpm-alpine

LABEL maintainer="Alex van Trirum <alex.vantrirum@bovemij.nl>"

COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/
COPY --from=composer:2.2 /usr/bin/composer /usr/bin/

RUN mv "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

RUN install-php-extensions apcu calendar gd gmp imagick intl igbinary mysqli opcache pdo_mysql redis soap ssh2 zip mcrypt sqlsrv pdo_sqlsrv memcached

RUN apk update
#RUN apk add --no-cache python3 build-base
RUN apk add --no-cache nodejs npm
RUN apk add --no-cache supervisor openssh

RUN npm install -g less
RUN apk add --no-cache gnu-libiconv

#CMD ["/usr/bin/supervisord", "-c", "/etc/supervisor/conf.d/supervisord.conf"]

ENV LD_PRELOAD /usr/lib/preloadable_libiconv.so

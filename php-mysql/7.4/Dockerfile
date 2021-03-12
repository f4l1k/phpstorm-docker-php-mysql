FROM php:7.4-apache
RUN apt update && apt install -y vim

RUN ["/bin/bash","-c","echo -e \"xdebug.remote_enable=On\nxdebug.remote_host=host.docker.internal\nxdebug.remote_port=9000\nxdebug.auto_trace=On\nxdebug.collect_vars=On\nxdebug.collect_return=On\nxdebug.collect_params=On\nxdebug.idekey=phpstorm\nxdebug.remote_log='/tmp/xdebug.log'\" >> /usr/local/etc/php/conf.d/myconfig.ini"]

RUN  docker-php-ext-install mysqli \
    && pecl install xdebug-2.9.0 \
    && docker-php-ext-enable xdebug

RUN apache2ctl restart
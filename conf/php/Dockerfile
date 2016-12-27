FROM phpdockerio/php7-fpm:latest

# Install selected extensions and other stuff
RUN apt-get update && apt-get -y --no-install-recommends install \
    git \
    curl \
    wget \
    php7.0-memcached \
    php7.0-mysql \
    php7.0-imagick \
    php7.0-imap \
    php7.0-intl \
    php7.0-mbstring \
    php7.0-soap \
    php7.0-xml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    /usr/local/bin/composer global require "fxp/composer-asset-plugin"

ENV GITHUB_TOKEN <replace token>

RUN composer config -g github-oauth.github.com ${GITHUB_TOKEN}

RUN mkdir -p /var/www/code/

COPY ./code/ /var/www/code

RUN cd /var/www/code && composer update

WORKDIR /var/www/code/

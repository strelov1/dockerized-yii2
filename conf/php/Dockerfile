FROM phpdockerio/php7-fpm:latest

# Install selected extensions and other stuff
RUN apt-get update && apt-get -y --no-install-recommends install \
    php7.0-memcached \
    php7.0-mysql \
    php7.0-imagick \
    php7.0-imap \
    php7.0-intl \
    php7.0-mbstring \
    php7.0-soap \
    php7.0-xml \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

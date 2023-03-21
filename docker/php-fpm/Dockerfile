FROM devilbox/php-fpm-8.1:latest
WORKDIR "/application"

# # Fix debconf warnings upon build
# ARG DEBIAN_FRONTEND=noninteractive

# # Install selected extensions and other stuff
# RUN apt-get update \
#     && apt-get -y --no-install-recommends install php8.1-mysql php8.1-gd php8.1-intl \
#     && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# # Install git
# RUN apt-get update \
#     && apt-get -y install git \
#     && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# RUN apt update && apt install -y software-properties-common

# RUN add-apt-repository ppa:ondrej/php

RUN apt update -y

RUN apt upgrade -y

RUN apt install -y git

RUN apt-get install libzip4 unzip

RUN docker-php-ext-install pdo_mysql
# RUN apt-get install -y zip unzip php8-zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sS https://get.symfony.com/cli/installer | bash

RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony
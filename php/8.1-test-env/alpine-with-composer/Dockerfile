FROM alpine:latest
WORKDIR /bin
RUN echo \
$'http://dl-cdn.alpinelinux.org/alpine/edge/main\n'\
$'http://dl-cdn.alpinelinux.org/alpine/edge/community\n'\
$'http://dl-cdn.alpinelinux.org/alpine/edge/testing\n'\
>> /etc/apk/repositories
RUN apk update
RUN apk add php81 php81-common\
            php81-xml php81-xmlwriter\
            php81-session\
            php81-tokenizer\
            php81-dom\
            php81-mbstring\
            php81-curl\
            php81-zip\
            php81-intl\
            php81-bz2\
            php81-opcache\
            php81-json\
            php81-phar\
            php81-openssl\
            php81-ctype\
            php81-iconv
RUN apk add curl\
            icu-data-full
RUN curl -sS https://getcomposer.org/installer | php
RUN chmod 755 composer.phar && chown root:root composer.phar
RUN mv composer.phar composer
RUN cp composer /usr/bin/composer
WORKDIR /

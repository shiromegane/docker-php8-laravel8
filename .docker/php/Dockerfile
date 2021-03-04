FROM php:8.0.2-fpm-alpine

ENV TZ=Asia/Tokyo \
    COMPOSER_ALLOW_SUPERUSER=1 \
    COMPOSER_HOME=/composer

RUN apk --update --upgrade add tzdata zsh git vim curl && \
    cp /usr/share/zoneinfo/${TZ} /etc/localtime && \
    rm -rf /var/cache/apk/* && \
    find / -type f -iname \*.apk-new -delete
#    apk del tzdata

ENV SHELL=/bin/zsh

COPY --from=composer:2.0.11 /usr/bin/composer /usr/bin/composer

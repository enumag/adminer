FROM dockette/alpine:3.5

MAINTAINER Milan Sulc <sulcmil@gmail.com>

ENV ADMINER_VERSION=4.3.1

RUN apk update && apk upgrade && \
    apk add \
        wget \
        ca-certificates \
        php5 \
        php5-mysql && \
    wget https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION.php -O /srv/index.php && \
    apk del wget ca-certificates && \
    rm -rf /var/cache/apk/*

WORKDIR srv
EXPOSE 80

CMD /usr/bin/php5 -S 0.0.0.0:80

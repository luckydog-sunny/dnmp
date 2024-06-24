ARG MINE_VERSION
FROM ${MINE_VERSION}


ARG CONTAINER_PACKAGE_URL

ENV TIMEZONE=${timezone:-"Asia/Shanghai"} \
    APP_ENV=prod \
    SCAN_CACHEABLE=(true)

WORKDIR /opt/www

ENTRYPOINT ["php", "/opt/www/mineadmin/bin/hyperf.php", "start"]
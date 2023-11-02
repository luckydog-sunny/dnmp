ARG MINE_VERSION
FROM ${MINE_VERSION}


ARG CONTAINER_PACKAGE_URL

ENV TIMEZONE=${timezone:-"Asia/Shanghai"} \
    APP_ENV=prod \
    SCAN_CACHEABLE=(true)


# update
RUN set -ex \
    # show php version and extensions
    && php -v \
    && php -m \
    && php --ri swoole \
    #  ---------- some config ----------
    && cd /etc/php* \
    # - config PHP
    && { \
        echo "upload_max_filesize=128M"; \
        echo "post_max_size=128M"; \
        echo "memory_limit=1G"; \
        echo "date.timezone=${TIMEZONE}"; \
    } | tee conf.d/99_overrides.ini \
    # - config timezone
    && ln -sf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
    && echo "${TIMEZONE}" > /etc/timezone \
    # ---------- clear works ----------
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man \
    && echo -e "\033[42;37m Build Completed :).\033[0m\n"

WORKDIR /opt/www


COPY ./www/MineAdmin /opt/www

# 修改composer镜像源
RUN composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/

# 安装composer依赖包
# RUN composer install --no-dev -o

# 文件权限问题
RUN chmod +x /opt/www/bin/hyperf.php


ENTRYPOINT ["php", "/opt/www/bin/hyperf.php", "start"]
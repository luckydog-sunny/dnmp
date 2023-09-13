ARG RABBITMQ_VERSION
ARG TZ

FROM ${RABBITMQ_VERSION}


# 设置时区(Mac 的格式)

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

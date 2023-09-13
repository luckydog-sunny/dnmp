ARG MYSQL8_VERSION
ARG TZ

FROM ${MYSQL8_VERSION}

# 设置时区 
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#RUN chmod 770 /var/log/mysql/
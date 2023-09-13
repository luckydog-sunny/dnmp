# 声明变量，变量值可通过docker-compose.yml文件传进来
ARG NGINX_VERSION
ARG TZ

# 基础镜像版本
FROM ${NGINX_VERSION}

# 设置时区
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 终端进入容器后，落脚目录
WORKDIR /www
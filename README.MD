1.目录结构
``` shell
/
├── data                        数据库数据目录
│   ├── mysql                   MySQL8 数据目录
├── services                    服务构建文件和配置文件目录
│   ├── mysql8                  MySQL8 配置文件目录
│   ├── nginx                   Nginx 配置文件目录
│   ├── php81                   PHP8.1 配置目录
│   ├── php74                   PHP7.4 配置目录
│   └── redis                   Redis 配置目录
├── logs                        日志目录
├── docker-compose.sample.yml   Docker 服务配置示例文件
├── env.smaple                  环境配置示例文件
└── www                         PHP 代码目录
```

2、安装
``` shell
# 进入到docker-compose.yml所在目录
cd /xxx/dnmp

# 复制环境变量文件
cp env.sample .env 

# 复制 docker-compose 配置文件。默认启动3个服务：
cp docker-compose.sample.yml docker-compose.yml   

# 构建镜像
docker-compose build        

# 启动容器
docker-compose up -d  

# 查看容器启动状态
docker-compose ps      
             
```
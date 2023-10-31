1.目录结构
``` shell
/
├── data                        数据库数据目录
│   ├── mysql8                  MySQL8 数据目录
│   ├── ...                     
├── services                    服务文件配置目录
│   ├── mysql8                  MySQL8   配置目录
│   ├── nginx                   Nginx    配置目录
│   ├── php81                   PHP8.1   配置目录
│   ├── php74                   PHP7.4   配置目录
│   ├── rabbitmq                Rabbitmq 配置目录
│   └── redis                   Redis    配置目录
│   └── ...                     
├── logs                        日志目录
├── docker-compose.yml          Docker 服务配置文件
├── env.smaple                  环境配置示例文件
└── www                         项目代码目录
```

2、安装
``` shell
# 进入到docker-compose.yml所在目录
cd /xxx/dnmp

# 复制环境变量文件
cp env.sample .env 

# 构建镜像
docker-compose build        

# 启动容器
docker-compose up -d  

# 查看容器启动状态
docker-compose ps      
             
```
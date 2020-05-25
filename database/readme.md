### 部署数据库（docker-compose）

执行下面的命令使用 docker-compose 部署 mysql、redis

```
    git clone https://github.com/usoftglobal/k8s-seckill.git

    cd k8s-seckill/database
    docker-compose up -d --build

    # 执行完成将暴露 3307、6399 端口
    # 连接到 mysql  服务器创建 seckill 数据库
    # 将 seckill.sql 导入到 seckill 数据库
```
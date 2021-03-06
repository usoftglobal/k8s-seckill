# 制作秒杀服务镜像

请在 kubernetes 主节点（非数据库服务器）执行

### 拉取秒杀项目代码

```
    cd k8s-seckill/image/src/github.com/usoftglobal
    git clone https://github.com/usoftglobal/seckill.git
```

### 更新数据库配置

使用 `vim seckill/config.yaml` 更新 mysql、redis 的配置信息（最好内网IP）

### 制作项目镜像

```
    cd k8s-seckill/image
    docker build -t usoftglobal/seckill:1.0.0 .

    # 查看刚制作的镜像
    docker images | grep seckill
```

### 创建、推送到远程容器

```
    # 创建你自己的容器镜像，比如（registry.cn-shanghai.aliyuncs.com/usoftglobal/seckill）
    # 登录远程容器账户
    docker login --username={你的用户名} registry.cn-shanghai.aliyuncs.com

    # 标记镜像关联到远程
    docker tag f335cd766090 registry.cn-shanghai.aliyuncs.com/usoftglobal/seckill:1.0.0

    # 推送 docker 镜像到远程
    docker push registry.cn-shanghai.aliyuncs.com/usoftglobal/seckill:1.0.0
```
# 部署秒杀服务

## 如何使用？

```
    git clone https://github.com/usoftglobal/k8s-seckill.git
    cd k8s-seckill
```

### 部署 MySQL、Redis

请按照 [./database/readme.md](database/readme.md) 执行

### 制作（更新）秒杀服务镜像

请按照 [./image/readme.md](image/readme.md) 执行

### 部署秒杀集群

```
    cd k8s-seckill

    # 执行部署
    kubectl applu -f seckill-deployment.yaml

    kubectl get pods
    ...
```
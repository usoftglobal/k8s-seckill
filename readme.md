# 部署秒杀服务


## 部署 MySQL、Redis（数据库节点单独部署）

请按照 [./database/readme.md](database/readme.md) 执行

## Kubernetes 集群节点部署

```
    git clone https://github.com/usoftglobal/k8s-seckill.git
    cd k8s-seckill
```

### 制作秒杀服务镜像

请按照 [./image/readme.md](image/readme.md) 执行

### 部署秒杀集群

```
    cd k8s-seckill

    # 执行部署
    kubectl applu -f seckill-deployment.yaml

    kubectl get pods
    ...
```
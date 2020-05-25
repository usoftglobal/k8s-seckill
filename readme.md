# 部署秒杀服务

## 1、部署 MySQL、Redis（数据库节点单独部署）

请按照 [./database/readme.md](database/readme.md) 执行

## 2、Kubernetes 集群节点部署

```
    git clone https://github.com/usoftglobal/k8s-seckill.git
```

### 2.1、制作秒杀服务镜像

请按照 [./image/readme.md](image/readme.md) 执行

### 2.2、部署秒杀集群

```
    cd k8s-seckill

    # 执行部署
    kubectl apply -f seckill-deployment.yaml

    # 查看 pod 状态，Running 正常
    kubectl get pods

    # 查看外部端口
    kubectl get services

    # 结果如下
    # NAME         TYPE        CLUSTER-IP    EXTERNAL-IP   PORT(S)          AGE
    # kubernetes   ClusterIP   10.96.0.1     <none>        443/TCP          15m
    # seckill      NodePort    10.111.1.62   <none>        3000:31806/TCP   44s
    
    # 访问测试
    http://你的公网IP:31806

    # 创建商品
    http://你的公网IP:31806/goodsCreate?number=10000

    # 秒杀下单
    http://你的公网IP:31806/seckill/buy?goods_id=1&number=10
```
# 使用 Kubernetes 部署 Golang 秒杀

### 如何部署？

```
git clone 当前项目

# clone 秒杀源码
cd k8s-seckill/deployments/source-code/src/github.com/usoftglobal/
git clone 秒杀项目源码

# 改改配置

# 使用 kubernetes 部署
cd k8s-seckill
kubectl apply -f local-volumes.yaml
kubectl applu -k deployments/kustomization.yaml

kubectl get pods
...
```
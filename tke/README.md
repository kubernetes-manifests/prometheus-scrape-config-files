# 腾讯云 TKE 集群中的监控抓取配置

## TKE 标准集群

- [非超级节点的容器监控 (cadvisor)](cadvisor-on-tke.yaml)
- [非超级节点的 kubelet 监控](kubelet-on-tke.yaml)
- [非超级节点的节点基础监控 (node-exporter)](node-exporter-on-tke.yaml)
- [非超级节点的健康检查健康监控 (就绪检查与存活检查探测结果)](probes-on-tke.yaml)
- [超级节点的 Pod 监控 (包含 Pod 子机维度和容器维度)](serverless-pod-on-standard-cluster.yaml) 

## TKE Serverless 集群

- [超级节点的 Pod 监控 (包含 Pod 子机维度和容器维度)](serverless-pod-on-serverless-cluster.yaml) 
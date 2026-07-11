# Loki Stack入门与实践示例

- getting-started: 单体部署，由docker-compose编排运行于单机环境，适合入门学习LogQL使用
- simple-scalable：简单可扩展模式部署，由docker-compose编排运行于单机环境，用于学习Loki Server的组件及功能
- promtail：在单独的主机上部署运行promtail，发现target并抓取其日志，并push到Loki Server
- kubernetes：在Kubernetes集群上部署Loki Stack的方式，主要基于helm进行
  - minio：基于MinIO Operator和CRD部署MinIO Cluster，支持持久存储，默认依赖于openebs-hostpath存储类；注意，MinIO要禁用tls；
  - loki：简单可扩展模式部署Loki Server，后端存储为部署于minio名称空间下的minio service，服务地址为“minio.minio.svc.cluster.local”；
  - promtail：基于DaemonSet部署promtail于Kubernetes集群，每个节点上的promtail pod部署基于容器日志文件的方式发现并抓取日志流；
  - grafana：部署grafana，支持持久化，默认创建两个Datasource
    - loki
    - prometheus





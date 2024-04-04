# Monitoring Automation

## Deploy kind cluster 
```shell
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.22.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

kind create cluster      # one-node k8s cluster
```

## Setup for metrics-server (required for nginx HPA) - Method 1:
- get https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml.
- patch metrics-server deployment with `--kubelet-insecure-tls`.
- apply components.yaml

## Deploy k8s objects to k8s cluster:
- Namespace first
- Nginx manifest files second

## Use metrics from prometheus to autoscale (required for nginx HPA) - Method 2 - TODO:
- https://towardsdatascience.com/kubernetes-hpa-with-custom-metrics-from-prometheus-9ffc201991e
- https://artifacthub.io/packages/helm/prometheus-community/prometheus-adapter

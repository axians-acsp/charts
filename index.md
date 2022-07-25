<p align="center">
  <img src="https://raw.githubusercontent.com/axians-acsp/charts/stable/.github/assets/axians_logo.png" />
</p>

# Axians Helm Charts Repository

Add Axians repository to Helm repos:

```bash
$ helm repo add acsp https://helm.acsp.io
```

## Install zabbix-kubernetes-discovery

### Install

```bash
$ kubectl create namespace zabbix-monitoring
$ helm upgrade --install zabbix-kubernetes-discovery \
    acsp/zabbix-kubernetes-discovery \
    --namespace zabbix-monitoring \
    --set namespace.name="zabbix-monitoring" \
    --set environment.ZABBIX_ENDPOINT="zabbix-proxy.example.com" \
    --set environment.KUBERNETES_NAME="kubernetes-cluster-name"
```

### Uninstall

```bash
$ helm uninstall zabbix-kubernetes-discovery \
    --namespace zabbix-monitoring
$ kubectl delete namespace zabbix-monitoring
```

For more details on installing Zabbix Kubernetes Discovery, please see the [chart readme](https://github.com/axians-acsp/zabbix-kubernetes-discovery/tree/main/helm).

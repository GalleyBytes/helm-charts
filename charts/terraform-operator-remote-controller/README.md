# terraform-operator-remote-controller

![Version: 1.0.2](https://img.shields.io/badge/Version-1.0.2-informational?style=flat-square) ![AppVersion: 1.1.0](https://img.shields.io/badge/AppVersion-1.1.0-informational?style=flat-square)

A Helm chart to deploy the terraform-operator-remote-controller

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install terraform-operator-remote-controller galleybytes/terraform-operator-remote-controller --namespace tf-system
```

## Values

| Key | Description | Default |
|---|---|---|
| image | `object` image repository and tag | `{"repository":"ghcr.io/galleybytes/terraform-operator-remote-controller","tag":"1.1.0"}` |
| env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. | `[]` |
| resources | `object` CPU/Memory request and limit configuration | `{"limits":{"cpu":"50m","memory":"32M"},"requests":{"cpu":"5m","memory":"32M"}}` |
| nodeSelector | `object` node labels for pod assignment | `{}` |
| tolerations | `list` List of node taints to tolerate | `[]` |
| affinity | `object` node/pod affinities | `{}` |

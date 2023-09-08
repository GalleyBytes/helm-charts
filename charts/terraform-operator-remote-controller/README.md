# terraform-operator-remote-controller

![Version: 1.0.7](https://img.shields.io/badge/Version-1.0.7-informational?style=flat-square) ![AppVersion: 1.2.3](https://img.shields.io/badge/AppVersion-1.2.3-informational?style=flat-square)

A Helm chart to deploy the terraform-operator-remote-controller

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install terraform-operator-remote-controller galleybytes/terraform-operator-remote-controller --namespace tf-system
```

## Values

| Key | Description | Default |
|---|---|---|
| image | `object` image repository and tag | `{"repository":"ghcr.io/galleybytes/terraform-operator-remote-controller","tag":"1.2.3"}` |
| env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. Values can be tpl ie `{{ .Values.CLIENT_NAME }}` where `CLIENT_NAME` can be defined elsewhere. | `[]` |
| resources | `object` CPU/Memory request and limit configuration | `{"limits":{"cpu":"50m","memory":"32M"},"requests":{"cpu":"5m","memory":"32M"}}` |
| nodeSelector | `object` node labels for pod assignment | `{}` |
| tolerations | `list` List of node taints to tolerate | `[]` |
| affinity | `object` node/pod affinities | `{}` |
| data.vcluster | `object` A preset options to render a volume/volumeMount and environment variable used to | `{"enabled":false,"manifest":"","prerender":false}` |
| data.vcluster.enabled | `bool` Enable configuring the vcluster | `false` |
| data.vcluster.prerender | `bool` Run the manifest thru a helm-template before applying using the values from the current helm release | `false` |
| data.vcluster.manifest | `string` The fully defined vCluster configuration | `""` |

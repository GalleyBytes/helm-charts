# terraform-operator-plugin-manager

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: 0.3.0](https://img.shields.io/badge/AppVersion-0.3.0-informational?style=flat-square)

A Helm chart to deploy the terraform-operator-plugin-manager - A webhook to mutate tf resources with plugins.

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install galleybytes/terraform-operator-plugin-manager --namespace tf-system
```

## Values

| Key | Description | Default |
|---|---|---|
| env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. | `[]` |
| image.repository | `string`  | `"ghcr.io/galleybytes/terraform-operator-plugin-manager"` |
| image.tag | `string`  | `"0.3.0"` |
| image.pullPolicy | `string`  | `"IfNotPresent"` |
| args | `list` additional args to pass to the command | `[]` |
| server.port | `int` The port the runtime exposes to connect to the webserver | `8443` |
| service.annotations | `object` Service annotations key/values for the service resource | `{}` |
| service.port | `int` the http or https port clients will use to access the `server.port` | `443` |
| service.type | `string` service type is one of ClusterIP | LoadBalancer | NodePort | `"ClusterIP"` |
| resources | `object` CPU/Memory request and limit configuration | `{}` |
| nodeSelector | `object` node labels for pod assignment | `{}` |
| tolerations | `list` List of node taints to tolerate | `[]` |
| affinity | `object` node/pod affinities | `{}` |
| plugins | `object` definitions of plugin definitions & task options. See values.yaml | `{}` |

# terraform-operator-api

![Version: 1.0.14](https://img.shields.io/badge/Version-1.0.14-informational?style=flat-square) ![AppVersion: 0.7.2](https://img.shields.io/badge/AppVersion-0.7.2-informational?style=flat-square)

A Helm chart to deploy the terraform-operator-api

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install galleybytes/terraform-operator-api --namespace tf-system
```

## Values

| Key | Description | Default |
|---|---|---|
| args | `list` Optional args to include for the command | `["use-service-host"]` |
| env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. | `[]` |
| image.tag | `string`  | `"0.7.2"` |
| server.port | `int` The port the runtime exposes to connect to the webserver | `5555` |
| service.annotations | `object` Service annotations key/values for the service resource | `{}` |
| service.port | `int` the http or https port clients will use to access the `server.port` | `80` |
| service.type | `string` service type is one of ClusterIP | LoadBalancer | NodePort | `"ClusterIP"` |
| resources | `object` CPU/Memory request and limit configuration | `{}` |
| nodeSelector | `object` node labels for pod assignment | `{}` |
| tolerations | `list` List of node taints to tolerate | `[]` |
| affinity | `object` node/pod affinities | `{}` |
| postgres | `object` Create a pvc backed postgres database. Not suitable for production use. | `enabled=false` |

# terraform-operator

![Version: 0.2.15](https://img.shields.io/badge/Version-0.2.15-informational?style=flat-square) ![AppVersion: v0.9.0-pre3](https://img.shields.io/badge/AppVersion-v0.9.0--pre3-informational?style=flat-square)

A Helm chart to deploy the terraform-operator Controller and CRD.

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install galleybytes/terraform-operator --namespace tf-system
```

## Upgrading the Custom Resource Definition

Helm does not have support at this time for upgrading or deleting CRDs. Instead, update CRDs manually by running

```
kubectl apply -f crds/terraform.yaml
```

## Values

| Key | Description | Default |
|---|---|---|
| controller.affinity | `object` node/pod affinities | `{}` |
| controller.args | `list` additional arguments for the command | <a href="values.yaml#L23-L25">values.yaml</a> |
| controller.enabled | `bool` deploy the terraform-operator controller | `true` |
| controller.environmentVars | `object` key/value envs | `{}` |
| controller.image.pullPolicy | `string` Set how kubernetes determines when to pull the docker image. | `"IfNotPresent"` |
| controller.image.repository | `string` repo name without the tag. The init container shares the name and appends `-gencert`. | `"isaaguilar/terraform-operator"` |
| controller.image.tag | `string` tag of the image | `"v0.9.0-pre3"` |
| controller.nodeSelector | `object` node labels for pod assignment | `{}` |
| controller.replicaCount | `int` number of replicas | `1` |
| controller.resources | `object` CPU/Memory request and limit configuration | <a href="values.yaml#L32-L38">values.yaml</a> |
| controller.tolerations | `list` List of node taints to tolerate | `[]` |
| webhook.enabled | `bool` enables the webhook - required most of the time | `true` |

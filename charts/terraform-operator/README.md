# terraform-operator

![Version: 0.2.20](https://img.shields.io/badge/Version-0.2.20-informational?style=flat-square) ![AppVersion: v0.9.0-alpha1](https://img.shields.io/badge/AppVersion-v0.9.0--alpha1-informational?style=flat-square)

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
| controller.args | `list` additional arguments for the command | <a href="values.yaml#L22-L24">values.yaml</a> |
| controller.enabled | `bool` deploy the terraform-operator controller | `true` |
| controller.env | `list` Env defined like k8s EnvFrom https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. Accepts `tpl` values. | `[]` |
| controller.environmentVars | `object` key/value envs | `{}` |
| controller.image.pullPolicy | `string` Set how kubernetes determines when to pull the docker image. | `"IfNotPresent"` |
| controller.image.repository | `string` image without the tag. | `"isaaguilar/terraform-operator"` |
| controller.image.tag | `string` tag of the image | `"v0.9.0-alpha1"` |
| controller.nodeSelector | `object` node labels for pod assignment | `{}` |
| controller.replicaCount | `int` number of replicas | `1` |
| controller.resources | `object` CPU/Memory request and limit configuration | <a href="values.yaml#L31-L37">values.yaml</a> |
| controller.tolerations | `list` List of node taints to tolerate | `[]` |
| webhook.enabled | `bool` enables the webhook - required most of the time | `true` |

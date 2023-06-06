# terraform-operator

![Version: 0.3.10](https://img.shields.io/badge/Version-0.3.10-informational?style=flat-square) ![AppVersion: v0.11.0](https://img.shields.io/badge/AppVersion-v0.11.0-informational?style=flat-square)

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
| controller.enabled | `bool` deploy the terraform-operator controller | `true` |
| controller.replicaCount | `int` number of replicas | `1` |
| controller.image.repository | `string` image without the tag. | `"isaaguilar/terraform-operator"` |
| controller.image.tag | `string` tag of the image | `"v0.11.0"` |
| controller.image.pullPolicy | `string` Set how kubernetes determines when to pull the docker image. | `"IfNotPresent"` |
| controller.args | `list` additional arguments for the command | <a href="values.yaml#L22-L24">values.yaml</a> |
| controller.resources | `object` CPU/Memory request and limit configuration | <a href="values.yaml#L31-L37">values.yaml</a> |
| controller.serviceAccount.create | `bool` creates the service account for the controller | `true` |
| controller.serviceAccount.extraAnnotations | `object` add extra annotations the service account | `{}` |
| controller.securityContext.runAsNonRoot | `bool` Allow running as root when false | `true` |
| controller.securityContext.runAsUser | `int` All processes run with user specified. This can be set to null for use on openshift | `1001` |
| controller.environmentVars | `object` key/value envs | `{}` |
| controller.env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. Accepts `tpl` values. | `[]` |
| controller.nodeSelector | `object` node labels for pod assignment | `{}` |
| controller.tolerations | `list` List of node taints to tolerate | `[]` |
| controller.affinity | `object` node/pod affinities | `{}` |
| webhook.enabled | `bool` enables the webhook - required most of the time | `true` |
| webhook.replicaCount | `int` number of replicas for the webhook | `2` |
| webhook.image.repository | `string` image without the tag. Usually the same as the controller | `"isaaguilar/terraform-operator"` |
| webhook.image.tag | `string` tag of the image | `"v0.11.0"` |
| webhook.image.pullPolicy | `string` Set how kubernetes determines when to pull the docker image. | `"IfNotPresent"` |
| webhook.args | `list` additional arguments for the command | <a href="values.yaml#L85">values.yaml</a> |
| webhook.resources | `object` CPU/Memory request and limit configuration | <a href="values.yaml#L91">values.yaml</a> |
| webhook.securityContext.runAsNonRoot | `bool` Allow running as root when false | `true` |
| webhook.securityContext.runAsUser | `int` All processes run with user specified. This can be set to null for use on openshift | `1001` |
| webhook.environmentVars | `object` key/value envs | `{}` |
| webhook.env | `list` Env defined like k8s EnvVar https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.21/#envvar-v1-core. Accepts `tpl` values. | `[]` |
| webhook.nodeSelector | `object` node labels for pod assignment | `{}` |
| webhook.tolerations | `list` List of node taints to tolerate | `[]` |
| webhook.affinity | `object` node/pod affinities | <a href="values.yaml#L117">values.yaml</a> |

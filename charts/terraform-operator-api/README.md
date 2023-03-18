# terraform-operator-api

![Version: 1.0.2](https://img.shields.io/badge/Version-1.0.2-informational?style=flat-square) ![AppVersion: 0.2.0](https://img.shields.io/badge/AppVersion-0.2.0-informational?style=flat-square)

A Helm chart to deploy the terraform-operator-api

## TL;DR;

```console
$ helm repo add galleybytes https://galleybytes.github.io/helm-charts
$ helm install galleybytes/terraform-operator-api --namespace tf-system
```

```
kubectl apply -f crds/terraform.yaml
```

## Values

| Key | Description | Default |
|---|---|---|
| deployment | `string`  | `"terraform-operator-api2"` |
| env | `list`  | `[]` |
| image.tag | `string`  | `"0.2.0"` |
| postgres.database.name | `string`  | `"tfoapi"` |
| postgres.enabled | `bool`  | `false` |
| postgres.name | `string`  | `"terraform-operator-api-postgres"` |
| postgres.server.port | `int`  | `5432` |
| postgres.server.storage | `string`  | `"100Mi"` |
| postgres.user.password | `string`  | `"password"` |
| postgres.user.username | `string`  | `"admin"` |
| server.port | `int`  | `5555` |

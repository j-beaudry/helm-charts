# Multitool

## TL;DR;

```console
$ helm repo add --username "__USERNAME__" --password "__PAT_TOKEN_WITH_ACCESS_TO_THE_REPO__" my-repo https://raw.githubusercontent.com/Dedalus-Clinalityx/helm-charts/gh-pages/
$ helm install my-release my-repo/multitool
```

## Introduction

This chart deploys  on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites


## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install my-release my-repo/multitool
```

The command deploys  on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Parameters

### Global parameters

| Name                      | Description                                      | Value |
| ------------------------- | ------------------------------------------------ | ----- |
| `global.imageRegistry`    | Global Docker registry                           | `""`  |
| `global.imagePullSecrets` | Global Docker registry secret names as an array  | `[]`  |
| `replicaCount`            | Number of replicas to deploy. Use an odd number. | `1`   |


### Common parameters

| Name                         | Description                                                                     | Value                      |
| ---------------------------- | ------------------------------------------------------------------------------- | -------------------------- |
| `nameOverride`               | String to partially override fullname template (will maintain the release name) | `""`                       |
| `fullnameOverride`           | String to fully override fullname template                                      | `""`                       |
| `namespaceOverride`          | String to fully override the default namespace                                  | `""`                       |
| `image.registry`             | Multitool image registry                                                        | `""`                       |
| `image.repository`           | Multitool image repository                                                      | `praqma/network-multitool` |
| `image.pullPolicy`           | Multitool image pull policy                                                     | `Always`                   |
| `image.digest`               | Multitool image digest, overrides image tag                                     | `""`                       |
| `image.tag`                  | Multitool image tag                                                             | `extra`                    |
| `image.pullSecrets`          | Specify docker-registry secret names as an array                                | `[]`                       |
| `extraEnvVars`               | Array containing extra env vars to configure Multiool                           | `{}`                       |
| `service.hostNetwork`        | Use Host network                                                                | `true`                     |
| `service.httpPort`           | Container Port for HTTP                                                         | `1180`                     |
| `service.httpsPort`          | Container Port for HTTPS                                                        | `11443`                    |
| `serviceAccount.create`      | Enable creation of ServiceAccount for Aiready pods                              | `false`                    |
| `serviceAccount.annotations` | Additional custom annotations for the ServiceAccount                            | `{}`                       |
| `serviceAccount.name`        | The name of the ServiceAccount to use.                                          | `""`                       |
| `podAnnotations`             | Additional pod annotations                                                      | `{}`                       |
| `podSecurityContext`         | Enable Pod Security Context                                                     | `{}`                       |
| `securityContext`            | Enable container security context                                               | `{}`                       |
| `resources.limits.cpu`       | CPU limit for the pod                                                           | `10m`                      |
| `resources.limits.memory`    | Memory limit for the pod                                                        | `20Mi`                     |
| `resources.requests.cpu`     | CPU request limit for the pod                                                   | `1m`                       |
| `resources.requests.memory`  | Memory request limit for the pod                                                | `20Mi`                     |
| `nodeSelector`               | Node labels for pod assignment                                                  | `{}`                       |
| `tolerations`                | Tolerations for pod assignment                                                  | `{}`                       |
| `affinity`                   | Affinity for pod assignment                                                     | `{}`                       |



Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example:


```console
$ helm install my-release my-repo/multitool --set replicaCount=1
```

Alternatively, a YAML file that specifies the values for the parameters can be provided while
installing the chart. For example:

```console
$ helm install my-release my-repo/multitool --values values.yaml
```

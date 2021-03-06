# sftpgo

![version: 0.0.9](https://img.shields.io/badge/version-0.0.9-informational?style=flat-square) ![type: application](https://img.shields.io/badge/type-application-informational?style=flat-square) ![app version: 1.2.2](https://img.shields.io/badge/app%20version-1.2.2-informational?style=flat-square) ![kube version: >=1.16](https://img.shields.io/badge/kube%20version->=1.16-informational?style=flat-square) [![artifact hub](https://img.shields.io/badge/artifact%20hub-sftpgo-informational?style=flat-square)](https://artifacthub.io/packages/helm/sagikazarmark/sftpgo)

Fully featured and highly configurable SFTP server with optional FTP/S and WebDAV support.

**Homepage:** <https://github.com/drakkan/sftpgo>

## TL;DR;

```bash
helm repo add skm https://charts.sagikazarmark.dev
helm install --generate-name --wait skm/sftpgo
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| replicaCount | int | `1` | Number of Pods to launch. |
| image.repository | string | `"ghcr.io/drakkan/sftpgo"` | Repository to pull the container image from. |
| image.pullPolicy | string | `"IfNotPresent"` | Image [pull policy](https://kubernetes.io/docs/concepts/containers/images/#updating-images) |
| image.tag | string | `""` | Overrides the image tag (default is the chart appVersion). |
| imagePullSecrets | list | `[]` | Image [pull secrets](https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/#create-a-pod-that-uses-your-secret) |
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| volumes | list | `[]` | Additional storage [volumes](https://kubernetes.io/docs/concepts/storage/volumes/) of a Pod. -- See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#volume-v1-core) for details. |
| volumeMounts | list | `[]` | Additional [volume mounts](https://kubernetes.io/docs/tasks/configure-pod-container/configure-volume-storage/) of a container. See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#volumemount-v1-core) for details. |
| envFrom | list | `[]` | Configure a [Secret](https://kubernetes.io/docs/concepts/configuration/secret/#using-secrets-as-environment-variables) or a [ConfigMap](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#configure-all-key-value-pairs-in-a-configmap-as-container-environment-variables) as environment variable sources for a Pod. See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#envfromsource-v1-core) for details. |
| serviceAccount.create | bool | `true` | Whether a service account should be created. |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account. |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template. |
| podAnnotations | object | `{}` | Custom annotations for a Pod. |
| podSecurityContext | object | `{}` | Pod [security context](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-pod). See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#podsecuritycontext-v1-core) for details. |
| securityContext | object | `{}` | Container [security context](https://kubernetes.io/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-container). See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#securitycontext-v1-core) for details. |
| service.annotations | object | `{}` | Custom annotations for the Service. |
| service.type | string | `"ClusterIP"` | Kubernetes [service type](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types). |
| service.port | int | `22` | Service port |
| service.externalTrafficPolicy | string | `nil` | Route external traffic to node-local or cluster-wide endoints. Useful for [preserving the client source IP](https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/#preserving-the-client-source-ip). |
| resources | object | No requests or limits. | Container resource [requests and limits](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/). See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#resourcerequirements-v1-core) for details. |
| autoscaling | object | Disabled by default. | Autoscaling configuration (see [values.yaml](values.yaml) for details). |
| nodeSelector | object | `{}` | [Node selector](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#nodeselector) configuration. |
| tolerations | list | `[]` | [Tolerations](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/) for node taints. See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#toleration-v1-core) for details. |
| affinity | object | `{}` | [Affinity](https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#affinity-and-anti-affinity) configuration. See the [API reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.20/#affinity-v1-core) for details. |

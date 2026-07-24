# EKS Kubernetes Resource Repository

This repository contains Kubernetes manifests used to create and manage application resources on an Amazon EKS cluster. The content is organized by Kubernetes resource type so that cluster resources can be maintained in a clean and predictable way.

## Repository structure

- `common/` - shared cluster objects such as namespaces, service accounts, RBAC, and other common resources
- `pods/` - standalone Pod manifests
- `deployments/` - Deployment manifests for stateless workloads
- `services/` - Service manifests for service discovery and traffic routing
- `configmaps/` - ConfigMap manifests for configuration data
- `secrets/` - Secret manifests for sensitive configuration values
- `statefulset/` - StatefulSet manifests for stateful workloads that require stable identity and persistent storage
- `storage/` - PersistentVolumeClaim and storage-related manifests
- `ingress/` - Ingress manifests for external HTTP/HTTPS access

Each folder contains a `manifests/` directory where the corresponding YAML resources are stored.

## Recommended usage

Apply resources in a logical order, starting with shared objects and dependencies:

1. `common/`
2. `configmaps/` and `secrets/`
3. `storage/`
4. `statefulset/` and `deployments/`
5. `services/`
6. `ingress/`

This layout makes it easier to maintain EKS manifests, understand the purpose of each resource, and organize YAML files as the cluster environment grows.

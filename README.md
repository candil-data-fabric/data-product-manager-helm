# Data Product Manager Helm Chart

## Current version: 3.3.2 (March 10th, 2025).

## Installation

**Initial requirements**

The Data Product Manager relies on [FluxCD](https://github.com/fluxcd/flux2) and on a custom [Kubernetes Cluster Role](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) for deploying Morph-KGC jobs/instances (for batch data products). Before installing the Helm Chart, deploy the Cluster Role and FluxCD (if needed):

```bash
$ git clone https://github.com/candil-data-fabric/data-product-manager.git
$ cd data-product-manager/kubernetes/
$ kubectl apply -f clusterRole.yaml # For the Cluster Role
$ kubectl apply -f fluxcd-flux2-v2.4.0.yaml # For FluxCD
```

### Using the Helm repository hosted in GitHub Pages

First, add the Helm repository:

```bash
$ helm repo add data-product-manager-helm https://candil-data-fabric.github.io/data-product-manager-helm/
```

Then, install the Helm Chart:

```bash
$ helm install data-product-manager data-product-manager-helm/data-product-manager
```

The chart will be installed using the default values. Use the provided [`values.yaml`](values.yaml) file in this repository as template to upgrade the installation with your desired parameters:

```bash
$ helm upgrade data-product-manager -f myvalues.yaml
```

To uninstall the Helm Chart, run the following command:

```bash
$ helm uninstall data-product-manager
```

### Cloning this repository

First, clone the repository:

```bash
$ git clone https://github.com/candil-data-fabric/data-product-manager-helm.git
```

Once cloned, edit the [`values.yaml`](values.yaml) file to match your deployment needs and run the following command:

```bash
$ helm install data-product-manager .
```

To uninstall the Helm Chart, run the following command:

```bash
$ helm uninstall data-product-manager
```

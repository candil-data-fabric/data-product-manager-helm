# Data Product Manager Helm Chart

## Current version: 3.3.3 (March 10th, 2025).

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

## Acknowledgements

This work was partially supported by the following projects:

- **Horizon Europe aerOS**: Autonomous, scalablE, tRustworthy, intelligent European meta Operating System for the IoT edge-cloud continuum. Grant agreement 101069732
- **SNS Horizon Europe ROBUST-6G**: Smart, Automated, and Reliable Security Service Platform for 6G. Grant agreement 101139068
- **UNICO 5G I+D 6G-DATADRIVEN**: Redes de próxima generación (B5G y 6G) impulsadas por datos para la fabricación sostenible y la respuesta a emergencias. Ministerio de Asuntos Económicos y Transformación Digital. European Union NextGenerationEU.
- **UNICO 5G I+D 6G-CHRONOS**: Arquitectura asistida por IA para 5G-6G con red determinista para comunicaciones industriales. Ministerio de Asuntos Económicos y Transformación Digital. European Union NextGenerationEU.

  ![UNICO](./images/ack-logo.png)

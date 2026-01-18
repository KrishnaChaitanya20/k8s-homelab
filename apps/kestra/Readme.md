## What is Kestra?

Kestra is a modern, open-source orchestration platform that helps automate workflows and processes, facilitating continuous integration and continuous delivery.

### What's in this folder?

This folder contains the necessary configuration files and scripts to deploy and manage a Kestra instance using kubernetes in kind clusters.

### How to deploy this app

#### Prerequisites
- A running Kubernetes cluster (e.g., kind, minikube, or any cloud provider)
- kubectl installed and configured to interact with your cluster
- Kustomize installed for managing Kubernetes configurations
- Ingress controller set up in your cluster (if you plan to use ingress for accessing Kestra)
- (Optional) ArgoCD installed if you plan to use it for deployment

#### Additional configurations

Before deploying Kestra, you may want to customize the configuration files to suit your specific requirements.

`kestra.config` contains configuration settings for Kestra, such as database connection details, authentication settings, and other application-specific configurations.

#### Deploying Kestra

cd into this folder and run the following command:

```bash
kubectl apply -k .
```

or if you are using argocd with CRD support enabled,
from the root of the repo, run:
```bash
kubectl apply -f argocd/applications/kestra.yaml
```

#### Accessing Kestra
Once deployed, you can access the Kestra instance using the service's external IP address or domain name, depending on your cluster's configuration.

If you are following my setup which is kind + ingress-nginx, you can access Kestra at:

http://kestra.localhost
 or 
the host/domain which you have set in ingress.yaml and kestra.config

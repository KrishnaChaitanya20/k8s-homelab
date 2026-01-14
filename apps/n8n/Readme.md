## What is N8n?

N8n is a free and open-source workflow automation tool that enables users to connect various applications and services to automate tasks and processes. It provides a visual interface for creating workflows, allowing users to define triggers, actions, and conditions without needing extensive coding knowledge. N8n supports a wide range of integrations with popular services like Google Sheets, Slack, Trello, and many others, making it a versatile solution for automating repetitive tasks and improving productivity.

### What's in this folder?

This folder contains the necessary configuration files and scripts to deploy and manage a N8n instance using kubernetes in kind clusters.

### How to deploy this app

#### Prerequisites
- A running Kubernetes cluster (e.g., kind, minikube, or any cloud provider)
- kubectl installed and configured to interact with your cluster
- Kustomize installed for managing Kubernetes configurations
- Ingress controller set up in your cluster (if you plan to use ingress for accessing N8n)
- (Optional) ArgoCD installed if you plan to use it for deployment

#### Additional configurations
Before deploying N8n, you may want to customize the configuration files to suit your specific requirements.

`config.properties`: This file contains configuration settings for N8n, such as database connection details, authentication settings, and other application-specific configurations.

#### Deploying N8n
cd into this folder and run the following command:

```bash
kubectl apply -k .
```

or if you are using argocd with CRD support enabled,
from the root of the repo, run:
```bash
kubectl apply -f argocd/applications/n8n.yaml
```

#### Accessing N8n
Once deployed, you can access the N8n instance using the service's external IP address or domain name, depending on your cluster's configuration.

If you are following my setup which is kind + ingress-nginx, you can access n8n at:

http://n8n.localhost
 or 
the host/domain which you have set in ingress.yaml and config.properties
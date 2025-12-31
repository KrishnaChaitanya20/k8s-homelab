# Kubernetes Homelab
This repo contains configuration files and documentation for setting up a Kubernetes homelab environment. The k8s cluster was setup using kind (Kubernetes IN Docker) for easy local development and testing. This is an evolution of my previous [Docker-based homelab](https://github.com/KrishnaChaitanya20/Docker_Homelab) as I transition services to Kubernetes.

> Note: This Kubernetes homelab configuration was developed on Windows 11 with Ubuntu WSL2, running Docker Engine within WSL2 and using Kind to manage Kubernetes clusters.

### Folder Structure
- `apps/`: Contains deployment manifests for various applications to be deployed on the Kubernetes cluster.(plain manifests or Kustomize templates)

- `argocd/`: Contains configuration files and manifests for deploying Argo CD, a GitOps continuous delivery tool.
    - `Readme.md`: Instructions for installing and configuring Argo CD in the Kubernetes cluster.
    - `applications/`: Contains Argo CD Application manifests for deploying applications via Argo CD.
    - `bootstrap/`: Contains bootstrap manifests for setting up Argo CD Ingress.
    - `app-of-apps.yaml`: manifest file for the App of Apps pattern in Argo CD.

- `infra/`: Contains infrastructure-related manifests and configurations, such as networking, storage, and monitoring components.
   - `kind-cluster.yaml`: Configuration file for creating a Kind Kubernetes cluster.

- `platform/`: Contains platform-level configurations and manifests that are essential for the overall operation of the Kubernetes cluster.
   - `ingress-nginx/`: Contains documentation for setting up ingress-nginx for kind clusters.
   - `prometheus-stack/`: Contains manifests and configurations for deploying the Prometheus monitoring stack(kube-prometheus-stack).
        - `ingress/`: Contains ingress config manifests for accessing Prometheus and Grafana dashboards.
   - `metallb` : Contains the documentation and manifest files for setting up a Layer 2 MetalLB service. 
      > This `MetalLB` setup is only for bare metal cluster and not needed for kind based clusters


### Future Improvements
- [ ] Create k8s cluster using kubeadm and migrate from kind to kubeadm.
- [ ] Migrate/Transition from Ingress to Gateway API.
- [ ] Change pv storage from hostPath to remote storage solution (NFS, Longhorn, etc.).
- [ ] Add more applications to the `apps/` directory for deployment via Argo CD.
   - Semaphore
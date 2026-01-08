## What is Jenkins?

Jenkins is a popular CI server that helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery.

### What's in this folder?

This folder contains the necessary configuration files and scripts to deploy and manage a Jenkins instance using kubernetes in kind clusters.

### How to deploy this app

cd into this folder and run the following command:

```bash
kubectl apply -k .
```

or if you are using argocd with CRD support enabled,
from the root of the repo, run:
```bash
kubectl apply -f argocd/applications/jenkins.yaml
```
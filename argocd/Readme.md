  ```
  kubectl create namespace argocd
  kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
  ```

  for ingress to fix too many redirects issue
  ```
  kubectl edit configmap -n argocd argocd-cmd-params-cm
  ```
  under data (add if not present) add the following line
  ```yaml
  server.insecure: "true"
  ```
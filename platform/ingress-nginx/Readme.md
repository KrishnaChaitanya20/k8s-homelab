### Deploying Ingress-NGINX on Kind
To deploy the Ingress-NGINX controller on a Kind (Kubernetes in Docker) cluster
  ```
  kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
  ```

### Deploying nginx-ingress Controller
To deploy the nginx-ingress controller in your Kubernetes cluster, you can use the following command:
to change any values refer to
  ```
  helm show values oci://ghcr.io/nginx/charts/nginx-ingress --version 2.4.0
  ```
create a values.yaml file
and change values accordingly in values.yaml file.

  ```
  helm install nginx-ingress oci://ghcr.io/nginx/charts/nginx-ingress --version 2.4.0 --skip-crds -f values.yaml -n nginx-ingress
  ```  
  

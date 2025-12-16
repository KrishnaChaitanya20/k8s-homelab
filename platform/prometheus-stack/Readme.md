### Adding the Prometheus Community Helm Chart Repository
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

### Installing the Prometheus Stack Helm Chart
```bash
helm install prometheus-stack prometheus-community/kube-prometheus-stack -f values.yml --namespace monitoring --create-namespace
```

### Apply Ingress Configuration
```bash
kubectl apply -f ingress/prometheus-ingress.yaml -n monitoring
kubectl apply -f ingress/grafana-ingress.yaml -n monitoring
```
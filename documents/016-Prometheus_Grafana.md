# Setup Prometheus Monitoring and Grafana on Kubernetes using Helm

---

## 1. Install Helm

```sh
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```

## 2. Add the Prometheus and Grafana Helm Repositories

```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

## 3. Create a namespace for monitoring:

```sh
kubectl create namespace monitoring
```

## 4. Install Prometheus using Helm

Install Prometheus

```sh
helm install prometheus prometheus-community/prometheus --namespace monitoring
```

## 5. Install Grafana using Helm

```sh
helm install grafana grafana/grafana --namespace monitoring
```

## 6. Access Prometheus and Grafana

### 6.1. Access Prometheus

```sh
kubectl --namespace monitoring port-forward svc/prometheus-server 9090:80
```

Open your browser and navigate to `http://localhost:9090`.

### 6.2. Access Grafana

```sh
kubectl --namespace monitoring port-forward svc/grafana 3000:80
```

Open your browser and navigate to `http://localhost:3000`.

## 7. Get Grafana Admin Password

The default username for Grafana is `admin`. You can get the admin password with the following command:

```sh
kubectl get secret --namespace monitoring grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```

## 8. Add Prometheus as a Data Source in Grafana

1. Login to Grafana (`http://localhost:3000`).
2. Go to Configuration > Data Sources.
3. Click on `Add data source`.
4. Select `Prometheus`.
5. Set the URL to `http://prometheus-server.monitoring.svc.cluster.local:80`.
6. Click `Save & Test`.

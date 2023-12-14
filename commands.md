## Install Mongodb-exporter
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

## install chart 
Install charts with all parameters needed. The chart will take values file as attribute and apply
the parameters in it.

```
helm install mongodb-exporter prometheus-community/prometheus-mongodb-exporter  -f values.yaml -n prometheus
```
Check that the chart has been installed (locaye the `mongo-db-exporter`) 
```
helm ls
```

```
kubectl get pods -n prometheus
```

Locate the pod  locate `mongo-exporter-prometheus-mongo-exporter-5tud9je...`

```
kubectl get svc -n prometheus
```
Locate the pod  locate `mongo-exporter-prometheus-mongo-exporter`


```
kubectl get servicemonitor -n prometheus
```
Check that the service monitor was created locate `mongo-exporter-prometheus-mongo-exporter`

Check the end point of the exporter at /metrics
```
kubectl get svc -n prometheus
```
locate `mongo-exporter-prometheus-mongo-exporter`
and run the command below to forward the port so that prometheus will discover the service and
scrape it's endpoint
```
kubectl port-forward service/mongodb-exporter-prometheus-mongodb-exporter 9216 -n prometheus
```
Alert manager UI
```
kubectl port-forward svc/prometheus-kube-prometheus-alertmanager 9093
```

## Grafana Dashboard credentials

### user: admin
### pwd: prom-operator (from values.yaml file set as default)


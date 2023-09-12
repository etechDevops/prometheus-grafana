## install chart
```
helm install mongodb-exporter prometheus-community/prometheus-mongodb-exporter  -f values.yaml -n prometheus
```
```
kubectl port-forward service/mongodb-exporter-prometheus-mongodb-exporter 9216 -n prometheus
``` 

## install chart with fixed version
```
helm install mongodb-exporter prometheus-community/prometheus-mongodb-exporter --version "2.8.1" 
```


## Link to chart
[https://github.com/prometheus-community/helm-charts/tree/main/charts/prometheus-mongodb-exporter]



## Grafana Dashboard credentials

### user: admin
### pwd: prom-operator (from values.yaml file set as default)


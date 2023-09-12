## install chart
```
helm install mongodb-exporter prometheus-community/prometheus-mongodb-exporter  -f values.yaml -n prometheus
```


```
kubectl port-forward service/mongodb-exporter-prometheus-mongodb-exporter 9216 -n prometheus
``` 


## Grafana Dashboard credentials

### user: admin
### pwd: prom-operator (from values.yaml file set as default)


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

Locate the pod locate  `mongo-exporter-prometheus-mongo-exporter-5tud9je...`


```
kubectl get pods -n prometheus
```

Locate the pod  locate `mongo-exporter-prometheus-mongo-exporter-5tud9je...`

```
kubectl get svc -n prometheus
```

Check that the service monitor was created locate `mongo-exporter-prometheus-mongo-exporter`
```
kubectl get servicemonitor -n prometheus
```

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


## Grafana Dashboard credentials

### user: admin
### pwd: prom-operator (from values.yaml file set as default)


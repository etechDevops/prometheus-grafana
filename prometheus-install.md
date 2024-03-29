Download scripts script and install helm
```
$curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
```
provide permission
```
sudo chmod 700 get_helm.sh
```
Execute script to install
```
sudo ./get_helm.sh
```
Check helm version
```
helm version --client
```

add the Helm Stable Charts for your local client
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://charts.helm.sh/stable
```
Create Prometheus namespace
```
kubectl create namespace prometheus
```
Install chart in prometheus namesapce
```
helm install prometheus prometheus-community/kube-prometheus-stack -n prometheus
```
If you encounter an error, run:
```
curl -L https://git.io/get_helm.sh | bash -s -- --version v3.8.2
```
Get pods and svc from prometheus namespace
```
kubectl get pods,svc -n prometheus
```

Edit Prometheus Service from clusterip to LB for external access
```
kubectl edit svc prometheus-kube-prometheus-prometheus -n prometheus
```
Edit Grafana service from clusterip to LB for external access
```
kubectl edit svc prometheus-grafana -n prometheus
```

```
kubectl get svc -n prometheus
```
userName: ```admin```

Password: ```prom-operator```



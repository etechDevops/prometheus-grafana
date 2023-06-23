Download scripts script and install helm
$curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
provide permission
$sudo chmod 700 get_helm.sh
Execute script to install
$sudo ./get_helm.sh
$helm version --client

add the Helm Stable Charts for your local client
$helm repo add stable https://charts.helm.sh/stable
$helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

Create Prometheus namespace
$kubectl create namespace prometheus
$helm install stable prometheus-community/kube-prometheus-stack -n prometheus

If you encounter an error, run:
$curl -L https://git.io/get_helm.sh |
bash -s -- --version v3.8.2

$kubectl get pods -n prometheus
$kubectl get svc -n prometheus

Edit Prometheus Service
$kubectl edit svc stable-kube-prometheus-sta-prometheus -n prometheus

Edit Grafana Service
$kubectl edit svc stable-grafana -n prometheus
$kubectl get svc -n prometheus
userName: admin
Password: prom-operator



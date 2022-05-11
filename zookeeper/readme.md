```
helm repo add bitnami https://charts.bitnami.com/bitnami

helm install zookeeper bitnami/zookeeper \
  --namespace zookeeper \
  --create-namespace \
  -f values.yaml

helm uninstall zookeeper --namespace zookeeper  

``` 
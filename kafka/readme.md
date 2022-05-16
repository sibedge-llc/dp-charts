```
helm repo add bitnami https://charts.bitnami.com/bitnami

helm install kafka bitnami/kafka \
  --namespace kafka \
  --create-namespace \
  -f values.yaml

helm uninstall kafka --namespace kafka

``` 
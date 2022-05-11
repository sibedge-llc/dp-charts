```
kubectl create namespace metallb

helm repo add metallb https://metallb.github.io/metallb
helm install  -n metallb metallb metallb/metallb -f values.yaml
```
```
helm repo add superset https://apache.github.io/superset

helm upgrade -i superset superset/superset \
	--values values.yaml \
    --namespace superset \
    --create-namespace 


helm uninstall superset --namespace superset  

```
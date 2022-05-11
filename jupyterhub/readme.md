helm repo add jupyterhub https://jupyterhub.github.io/helm-chart/
helm repo update

helm install jupyterhub jupyterhub/jupyterhub \
  --namespace jupyterhub \
  --create-namespace \
  --version=1.2.0 \
  --values values.yaml


helm upgrade --cleanup-on-fail jupyterhub jupyterhub/jupyterhub \
  --namespace jupyterhub \
  --version=1.2.0 \
  --values values.yaml


# Hub Config map editor:
We need open ports for spark in singleuser containers, so wee need to ad this lines to `hub` 
```python
  c.KubeSpawner.extra_pod_config = {
    'ports': [{
            'containerPort': 2222, 
            'name': 'driver', 
            'protocol': 'TCP'
        }, {
            'containerPort': 4040, 
            'name': 'spark-ui', 
            'protocol': 'TCP'
        }, {
            'containerPort': 7777, 
            'name': 'blockmanager', 
            'protocol': 'TCP'
        }
    ]

}
```

`kubectl create serviceaccount -n jupyterhub spark`
`kubectl create rolebinding spark-role --clusterrole=edit --serviceaccount=jupyterhub:spark --namespace=default` 


# TODO:

- Network Policy tunnig for Spark in clien mode
  Remove:
  ```yaml
  singleuser: 
  networkPolicy:
    enabled: false
  ```
  Add correct policy to `networkPolicy`

- Check if solution with gettings Pod IP with external Env is good idea, may be create an additional service for each Pod with predefined name.
- Spark, Hadoop and others configs export to ConfigMap for mounting in each Spark Pod
- Make Spark context availble on the start of JupyterLab 
- Full integration of `jupyterlab-sparkmonitor`


# Build and deploy Images:

## Spark:
``


## Hub: 
``

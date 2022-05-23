1. The installation implies to be used within Vultr infrastructure cloud platform
   Please refer [Getting Start with Helm on Windows](https://www.vultr.com/docs/getting-started-with-helm-on-windows) for details
2. Ensure [vultr storage](https://www.vultr.com/docs/block-storage/) is enabled
3. Edit or disable `global->storageClass` value in [values.yaml](./values.yaml) file in case you use different K8s plaform
4. Edit [values.yaml](./values.yaml) to turn up the postgres along [Bitnami](https://hub.docker.com/r/bitnami/postgresql/) recommendations
5. Run install with Helm 
```
helm repo add bitnami https://charts.bitnami.com/bitnami

helm install postgresql bitnami/postgresql \
  --namespace postgresql \
  --create-namespace \
  -f values.yaml
```
6. Run uninstall in case postgres is not needed anymore
```
helm uninstall postgresql --namespace postgresql

```

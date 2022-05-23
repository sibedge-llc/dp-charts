1. The installation implies to be used within Vultr infrastructure cloud platform
   Please refer [Getting Start with Helm on Windows](https://www.vultr.com/docs/getting-started-with-helm-on-windows) for details
2. Ensure [vultr storage](https://www.vultr.com/docs/block-storage/) is enabled
3. Edit or disable `global->storageClass` value in [values.yaml](./values.yaml) file in case you use different K8s plaform
4. Edit [values.yaml](./values.yaml) to turn up the kafka/zookeeper along [Bitnami](https://hub.docker.com/r/bitnami/kafka/) recommendations
5. Run install with Helm
```
helm repo add bitnami https://charts.bitnami.com/bitnami

helm install kafka bitnami/kafka \
  --namespace kafka \
  --create-namespace \
  -f values.yaml
```
6. Run uninstall in case kafka/zookeeper is not needed anymore
```
helm uninstall kafka --namespace kafka
```

# SPARK 
```Bash
helm repo add spark-operator https://googlecloudplatform.github.io/spark-on-k8s-operator
 
kubectl apply -f namespace.yaml

helm install spark spark-operator/spark-operator \
	--namespace spark-operator \
	--create-namespace \
	--set sparkJobNamespace=spark-jobs \
	--set serviceAccounts.spark.name=spark \
	--set webhook.enable=true \
	--set enableBatchScheduler=true \
	--set image.tag=v1beta2-1.3.3-3.1.1 \
	--set image.repository=ghcr.io/googlecloudplatform/spark-operator

helm upgrade --install spark spark-operator/spark-operator \
	--namespace spark-operator \
	--create-namespace \
	--set sparkJobNamespace=spark-jobs \
	--set serviceAccounts.spark.name=spark \
	--set webhook.enable=true \
	--set enableBatchScheduler=true \
	--set image.tag=v1beta2-1.3.3-3.1.1 \
	--set image.repository=ghcr.io/googlecloudplatform/spark-operator
 
helm uninstall -n spark-operator spark

```

```Bash
helm status -n spark-operator spark
```

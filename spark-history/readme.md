helm repo add stable https://charts.helm.sh/stable

helm install spark-history-server stable/spark-history-server \
	 -f config.yaml
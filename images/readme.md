# Images

## Spark
```bash
git clone git@github.com:apache/spark.git
git checkout -b branch-3.2  origin/branch-3.2
git checkout tags/v3.2.0
```

```
./bin/docker-image-tool.sh -u root -r skhakhulin -t 3.2.0-hadoop-3.3.1 -p kubernetes/dockerfiles/spark/bindings/python/Dockerfile build

docker tag itayb/spark-py:3.2.0-hadoop-3.3.1 skhakhulin/spark:3.2.0-hadoop-3.3.1
```

./bin/docker-image-tool.sh \ 
	-r <repo> \ 
	-t my-tag \ 
	-p ./kubernetes/dockerfiles/spark/bindings/python/Dockerfile \ 
	-b java_image_tag=11-jre-slim \
	build

## JupyterLab

```bash
docker build -t skhakhulin/jupyterlab:3.2.4-spark-3.2.0-hadoop-3.3.1-java-11-scala-2.12-python-3.8-v1 .
```

## Airflow


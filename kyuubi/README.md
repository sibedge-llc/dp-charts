## Установка Kyuubi

Чарта нет в публичном репо, можно только локально забрать из их гит-репозитория, плюс тут дописано всякое.

Нужно два экземпляра kyuubi - один для дата-инженеров с возможностью создавать-удалять схемы в метасторе и делать всё в бакете, и второй для аналитиков с read only в метасторе и read only кроме папки analytics в s3.

Экземпляр DE:

```console
helm template de . -f values.yaml -n kyuubi

helm install de . -f values.yaml -n kyuubi --timeout 300s

helm upgrade --cleanup-on-fail --atomic de . -f values.yaml -n kyuubi --timeout 180s


helm template kyuubi . \
    --namespace kyuubi \
	--create-namespace \
	-f values.yaml


helm install kyuubi . \
    --namespace kyuubi \
	--create-namespace \
	-f values.yaml

helm upgrade kyuubi . \
    --namespace kyuubi \
	--create-namespace \
	-f values.yaml

helm uninstall kyuubi --namespace kyuubi  



```
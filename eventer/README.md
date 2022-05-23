1. The installation implies to be used within Vultr infrastructure cloud platform
   Please refer [Getting Start with Helm on Windows](https://www.vultr.com/docs/getting-started-with-helm-on-windows) for details
2. The eventer requires kafka and postgres instances.
   See [/kafka/README.md](./kafka/README.md) and [/postgres/README.md](./postgres/README.md) for details
3. Update `config -> kafka` in [./values.yaml](./values.yaml#L21-L22) and `config -> postgres` in [./values.yaml](./values.yaml#L24-L29) settings according to settings used in 
   corresponded [kafka/values.yaml](../kafka/values.yaml) and [postgres/values.yaml](../postgres/values.yaml)
4. In case kafka service has different name - update ExternalName in `spec -> externalName` in [templates/kafka.yaml](./templates/kafka.yaml)
5. In case postgres service has different name - update ExternalName in `spec -> externalName` in [templates/postgresql.yaml](./templates/postgresql.yaml)
6. Install eventer to cluster via command
```bash
helm upgrade --install eventer eventer/ \
  --namespace eventer \
  --create-namespace \
  -f eventer/values.yaml
```
7. To uninstall service use following command
```
helm uninstall eventer --namespace eventer
```
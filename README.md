# dp-charts
Data Warehouse Platform Helm Charts

# Create new configs
```Python 
  pip3 install -r requirements.txt
  cp -rfp inventory/sample inventory/test_spark
```

# Generate hosts file

Hosts ip `149.28.55.222 63.209.32.78 149.28.233.39 208.167.245.23`

Generate inventory file
```Bash 
CONFIG_FILE=inventory/test_spark/hosts.yaml KUBE_CONTROL_HOSTS=1 python3 contrib/inventory_builder/inventory.py 149.28.55.222 63.209.32.78 149.28.233.39 208.167.245.23
``` 

Set in inventory/test_spark/group_vars/k8s_cluster:
```Yaml
# Make a copy of kubeconfig on the host that runs Ansible in {{ inventory_dir }}/artifacts
kubeconfig_localhost: true
# Download kubectl onto the host that runs Ansible in {{ bin_dir }}
kubectl_localhost: true
```
# Install k8s
```Bash
ansible-playbook -i inventory/test_spark/hosts.yaml  --become --become-user=root --user root cluster.yml 
```

 ## TODO:
  - Check https://github.com/datamechanics/delight/blob/main/documentation/spark_operator.md

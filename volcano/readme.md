## Install to k8s:
`kubectl apply -f volcano-1.4.0/installer/volcano-development.yaml`

## Install volcano monitoring
`kubectl apply -f volcano-1.4.0/installer/volcano-monitoring-latest.yaml`

## Create Queue
`kubectl apply -f queue.yaml`

and in Spark Application manifest 

```YAML 
BatchSchedulerOptions:
	queue: "queue1"
```

## Create Priority Class
`kubectl apply -f queue.yaml`

and in Spark Application manifest 

```YAML 
BatchSchedulerOptions:
	priorityClassName: "pri1"
```
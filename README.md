# Sensu Stackdriver Kube

This projects demonstrates Sensu Go feeding monitoring data into Google Stackdriver.

## Kube Deploy

```
kubectl apply -f kube/sensu.yml

kubectl get pods --namespace sensu-stackdriver

kubectl get services --namespace sensu-stackdriver
```

## Workstation Setup

[Install sensuctl](https://docs.sensu.io/sensu-go/latest/installation/install-sensu/#install-sensuctl).

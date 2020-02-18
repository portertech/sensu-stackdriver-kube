# Sensu Stackdriver Kube

This project demonstrates Sensu Go feeding monitoring data into Google Stackdriver.

## Kube Deploy

Create the `sensu-stackdriver` namespace.

```
kubectl apply -f kube/namespace.yml
```

Create the `stackdriver` secret containing the Google Stackdriver project id. Be sure to change `CHANGEME`!

```
kubectl create secret generic stackdriver --from-literal=project-id='CHANGEME' --namespace sensu-stackdriver
```

Deploy the Sensu cluster.

```
kubectl apply -f kube/sensu.yml
```

Deploy the demo web application.

```
kubectl apply -f kube/dummy.yml
```

List pods and services.

```
kubectl get pods --namespace sensu-stackdriver

kubectl get services --namespace sensu-stackdriver
```

## Workstation Setup

[Install sensuctl](https://docs.sensu.io/sensu-go/latest/installation/install-sensu/#install-sensuctl).

## Monitoring

```
sensuctl create -r -f sensu/
```

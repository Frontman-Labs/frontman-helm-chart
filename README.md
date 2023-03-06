# frontman-helm-chart

## package
this will create a tgz of the chart
```
helm package frontman
```


## install
take note of the file outputted as will be version specific
```
helm install frontman frontman-gateway-1.0.0.tgz
```


## review
Review the deployed chart
```
helm list -n default
```

Review the artefacts created from the chart
```
kubectl describe deployment frontman
```

```
kubectl describe svc frontman-gateway
```

```
kubectl describe ingress frontman-gateway-ingress
```


## uninstall
```
helm uninstall frontman
```

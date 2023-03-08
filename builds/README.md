![Logo](/assets/logo.png)
# Frontman

## install
Add the helm repository
```
helm repo add frontman https://frontman-labs.github.io/frontman-helm-chart/builds/
```

install the chart
```
helm install my-frontman-gateway frontman/frontman-gateway --version 0.0.1
```


## review
Review the deployed chart
```
helm list -n default
```

### Deployment of the APIM
```
kubectl describe deployment my-frontman-gateway
```

### The Service exposed
```
kubectl describe svc frontman-gateway
```

### Ingress
```
kubectl describe ingress frontman-gateway-ingress
```


## uninstall
```
helm uninstall my-frontman-gateway
```


## Contributing
If you'd like to contribute to Frontman, please fork the repository and submit a pull request. We welcome bug reports, feature requests, and code contributions.

## License
Frontman is released under the GNU General Public License. See LICENSE for details.
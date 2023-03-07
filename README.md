![Logo](/assets/logo.png)
# Frontman Helm Chart
Frontman can easily be installed using the provided helm chart. This helm chart is available on artifacthub.io

<p>&nbsp;</p>

[![Go Report Card](https://goreportcard.com/badge/github.com/Frontman-Labs/frontman)](https://goreportcard.com/report/github.com/Frontman-Labs/frontman) [![GitHub license](https://img.shields.io/github/license/Frontman-Labs/frontman)](https://github.com/Frontman-Labs/frontman/blob/main/LICENCE) ![GitHub go.mod Go version](https://img.shields.io/github/go-mod/go-version/Frontman-Labs/frontman)[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/frontman)](https://artifacthub.io/packages/search?repo=frontman)
<br />

## Glossary

- [Helm](#helm)
  - [Package](#package)
  - [Index](#index)
  - [Install](#install)
  - [Review](#review)
  - [Uninstall](#uninstall)
- [Contributing](#contributing)
- [License](#license)

## Helm
### package
this will create a tgz of the chart
```
helm package frontman --app-version 0.0.1 --version 0.0.1  --destination builds/
```

### index
```
helm repo index builds
```

## install
take note of the file outputted as will be version specific
```
helm install frontman frontman-gateway-0.0.1.tgz
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


## Contributing
If you'd like to contribute to Frontman, please fork the repository and submit a pull request. We welcome bug reports, feature requests, and code contributions.

## License
Frontman is released under the GNU General Public License. See LICENSE for details.
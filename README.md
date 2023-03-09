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
- [Actions](#actions)
- [Contributing](#contributing)
- [License](#license)

## Helm
### package
this will create a tgz of the chart
```
helm package frontman --app-version 0.0.1 --version 0.0.1  --destination builds/
```

obviously, we want to sign it - so assuming you have the correct rights to the correct key
```
helm package --sign --key "<name>" --keyring secring.gpg frontman --app-version 0.0.1 --version 0.0.1 --destination builds/
```

### index
```
helm repo index builds
```

### install
take note of the file outputted as will be version specific
```
helm install frontman frontman-gateway-0.0.1.tgz
```


### review
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


### uninstall
```
helm uninstall frontman
```

## Actions
For github actions, we test using Act. You can use the example below to trigger this locally for packaging the helm chart.

To run this test, you will need to create a GPG key. Ensure you provide the key name as `frontman`. Also ensure you **DO** choose a passphrase, as this is expected in the action.
```bash
gpg --full-generate-key
```

export the secring:
```bash
gpg --export-secret-keys >./secring.gpg
```

You will be required to create two files. These emulate the values available in github:
```yaml
# my.inputs
image=hyperioxx/frontman:latest
version=0.0.1
```

```yaml
# my.secrets
GITHUB_TOKEN=<PAT Token>
PAT=<PAT Token>
SECRING=<BASE64 encoded Secring.gpg>
HELM_KEY_PASSPHRASE=frontman2023
```

Now you can run `act` to run the action (add the additional parameter `--reuse` to persist the docker container created to act as the runner. You have `exec` into this using docker to verify things installed and/or files generated etc).
```bash
act workflow_call --input-file my.inputs --secret-file my.secrets
```


## Contributing
If you'd like to contribute to Frontman, please fork the repository and submit a pull request. We welcome bug reports, feature requests, and code contributions.

## License
Frontman is released under the GNU General Public License. See LICENSE for details.
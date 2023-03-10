# frontman-gateway

![Version: 0.0.4](https://img.shields.io/badge/Version-0.0.4-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.4](https://img.shields.io/badge/AppVersion-0.0.4-informational?style=flat-square)

A Helm chart for deploying the Frontman API Gateway

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Simon Chapman | <simonchapman1986@gmail.com> | <https://frontman-labs.github.io/frontman/> |
| Aaron Parfitt | <aaronparfitt@protonmail.com> | <https://frontman-labs.github.io/frontman/> |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| domain.api | string | `"example.com"` |  |
| domain.gateway | string | `"gateway.example.com"` |  |
| gateway.apiAddr | string | `"0.0.0.0:8080"` |  |
| gateway.apiSslCertPath | string | `"/certs/server.crt"` |  |
| gateway.apiSslEnabled | bool | `true` |  |
| gateway.apiSslKeyPath | string | `"/certs/server.key"` |  |
| gateway.gatewayAddr | string | `"0.0.0.0:8000"` |  |
| gateway.gatewaySslCertPath | string | `"/certs/server.crt"` |  |
| gateway.gatewaySslEnabled | bool | `true` |  |
| gateway.gatewaySslKeyPath | string | `"/certs/server.key"` |  |
| gateway.image | string | `"hyperioxx/frontman:latest"` |  |
| gateway.mongoUrl | string | `"mongodb://mongo:27017"` |  |
| gateway.serviceType | string | `"yaml"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)

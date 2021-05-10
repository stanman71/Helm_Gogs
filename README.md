# Gogs Helm Chart

[Gogs][] is a painless self-hosted Git service.

## Introduction

This chart bootstraps a [Gogs][] deployment on a [Kubernetes][] cluster using
the [Helm][] package manager.

## Configuration

The following table lists some of the configurable parameters of the Gogs
chart and their default values.

| Parameter                        | Description                                                  | Default                                                    |
| -----------------------          | ----------------------------------                           | ---------------------------------------------------------- |
| `image.repository`               | Gogs image                                                   | `gogs/gogs`                                                |
| `image.tag`                      | Gogs image tag                                               | `0.11.86`                                                  |
| `image.pullPolicy`               | Gogs image pull policy                                       | `Always` if `imageTag` is `latest`, else `IfNotPresent`    |
| `postgresql.install`             | Weather or not to install PostgreSQL dependency              | `true`                                                     |
| `postgresql.postgresHost`        | PostgreSQL host (if `postgresql.install == false`)           | `nil`                                                      |
| `postgresql.postgresUser`        | PostgreSQL User to create                                    | `gogs`                                                     |
| `postgresql.postgresPassword`    | PostgreSQL Password for the new user                         | `gogs`                                                     |
| `postgresql.postgresDatabase`    | PostgreSQL Database to create                                | `gogs`                                                     |
| `postgresql.postgresSSLMode`     | PostgreSQL SSL Mode                                          | `disable`                                                  |
| `postgresql.persistence.enabled` | Enable PostgreSQL persistence using Persistent Volume Claims | `true`                                                     |
| `serviceType`                    | The type of service to create (`ClusterIP`, `NodePort`, `LoadBalancer`) | `NodePort`                                      |
| `service.loadBalancerIP`         | The IP address to use when using serviceType `LoadBalancer`  | `nil`                                                      |
| `service.httpNodePort`           | Enable a static port where the Gogs http service is exposed on each Node’s IP | `nil`                                     |
| `service.sshNodePort`            | Enable a static port where the Gogs ssh service is exposed on each Node’s IP | `nil`                                      |

See [values.yaml](values.yaml) for a more complete list, and links to the Gogs documentation.

[Gogs]: https://github.com/gogits/gogs
[Kubernetes]: https://kubernetes.io
[Helm]: https://helm.sh

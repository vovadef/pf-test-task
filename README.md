# my-stack

my-stack is a Kubernetes demo application to automate the deploying nginx, postgres and redis services.

## Prerequisites

- Kubernetes 1.7+

## Installing the Chart

Full installation instructions, including details on how to configure extra
functionality in cert-manager can be found in the [getting started docs](https://helm.sh/docs/intro/install/).

To install the chart with the release name `my-stack`:

```console
$ kubectl create ns <deployment-namespace>

## Install the my-stack helm chart
$ cd my-stack
$ helm dependency build
$ cd ../ &&  helm install my-stack my-stack --set persistence.existingClaim=postgresql-pv --set volumePermissions.enabled=true
```

> **Tip**: List all releases using `helm list`

## Upgrading the Chart

```console
helm upgrade --install my-stack my-stack
```

## Uninstalling the Chart

To uninstall/delete the `my-stack` deployment:

```console
$ helm delete my-stack
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the my-stack chart and their default values.

| Parameter                                       | Description                                                                                                                              | Default                                   |
|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| `DB_HOST`                                       | Postgres DB host                                                                                                                         | `postgresql`                              |
| `DB_USER`                                       | Postgres username                                                                                                                        | `postgres`                                |
| `DB_NAME`                                       | Database name                                                                                                                            | `test`                                    |
| `DB_PORT`                                       | Database port                                                                                                                            | `5432`                                    |
| `REDIS_HOST`                                    | Redis host                                                                                                                               | `redis`                                   |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install --name my-stack -f values.yaml .
```
> **Tip**: You can use the default [values.yaml](values.yaml)

## Contributing

This chart is maintained by Volodymyr Tymchyshyn ( @vovadef )

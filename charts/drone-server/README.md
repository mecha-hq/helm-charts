# Mecha CI's Drone Server Helm Chart

[Drone](https://www.drone.io/) is a Continuous Integration platform built on container technology with native Kubernetes support.

This Chart is for installing [Drone server](https://docs.drone.io/server/overview/).

## Installing Drone server

See the [drone chart installation guide](./docs/install.md).

## Configuring Drone server

See [values.yaml](values.yaml) to see the Chart's default values. Refer to the [Drone server reference](https://docs.drone.io/server/reference/) for a more complete list of options.

To adjust an existing Drone install's configuration:

```console
# If you have a values file:
helm upgrade drone mecha-ci/drone-server --namespace drone --values drone-values.yaml
# If you want to change one value and don't have a values file:
helm upgrade drone mecha-ci/drone-server --namespace drone --reuse-values --set someKey=someVal
```

## Upgrading Drone server

Read the [release notes](https://github.com/harness/drone/blob/master/CHANGELOG.md) to make sure there are no backwards incompatible changes. Make adjustments to your values as needed, then run `helm upgrade`:

```console
# This pulls the latest version of the drone chart from the repo.
helm repo update
helm upgrade drone mecha-ci/drone-server --namespace drone --values drone-values.yaml
```

## Uninstalling Drone server

To uninstall/delete the `drone` deployment in the `drone` namespace:

```console
helm delete drone --namespace drone
```

Substitute your values if they differ from the examples. See `helm delete --help` for a full reference on `delete` parameters and flags.

## Support

For questions, suggestions, and discussion, visit the [Harness community site](https://community.harness.io/).

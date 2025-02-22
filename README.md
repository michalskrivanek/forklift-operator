# Forklift Operator

[![Operator Repository on Quay](https://quay.io/repository/konveyor/forklift-operator/status "Operator Repository on Quay")](https://quay.io/repository/konveyor/forklift-operator) [![License](http://img.shields.io/:license-apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0.html) [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/konveyor/forklift-operator/pulls)

Forklift Operator installs a suite of migration tools that facilitate the migration of VM workloads to [OpenShift Virtualization](https://cloud.redhat.com/learn/topics/virtualization/).

## Prerequisites

* [__OpenShift 4.9+__](https://www.openshift.com/)
* [__OpenShift Virtualization 4.9+__](https://www.redhat.com/en/technologies/cloud-computing/openshift/)

## Compatibility

Forklift depends on OpenShift Virtualization, see the table below for supported configurations:

Forklift release | OpenShift Virtualization release | OpenShift release
--- | --- | ---
v2.2.x | v4.9 | ```v4.9```
v2.3.x | v4.10+ | ```v4.10+```

**Note:** Please keep in mind Forklift Operator will not deploy in unsupported configurations.

## Forklift Operator Installation

Forklift Operator is installable on OpenShift 4 via OKD community operators.

### Installing _released versions_

1. Visit the OpenShift Web Console.
1. Navigate to _Operators => OperatorHub_.
1. Search for _Forklift Operator_.
1. Install the desired _Forklift Operator_ version.

### Installing _latest_

Installing latest is almost an identical procedure to released versions but requires creating a new catalog source.

1. `oc create -f forklift-operator-catalog.yaml`
1. Follow the same procedure as released versions until the Search for _Forklift Operator_ step.
1. There should be two _Forklift Operator_ available for installation now.
1. Select the _Forklift Operator_ without the _community_ tag.
1. Proceed to install latest.

**Note:** Installing _Latest_ will also include OLM channels for released versions.

### Installing _latest_ on Kubernetes

See [k8s.md](./docs/k8s.md) for details.

## ForkliftController CR Creation

1. Visit OpenShift Web Console, navigate to _Operators => Installed Operators_.
1. Select _Forklift Operator_.
1. Locate _ForkliftController_ on the top menu and click on it.
1. Adjust settings if desired and click Create instance.

## Customize Settings

Custom settings can be applied by editing the `ForkliftController` CR.

`oc edit forkliftcontroller -n konveyor-forklift`

## Forklift Documentation

See the [Forklift Documentation](https://konveyor.github.io/forklift/) for detailed installation instructions as well as how to use Forklift.

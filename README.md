# Cadence Charts

This repo contains Cadence helm chart maintained by original Cadence team @Uber.
This is an early version with known gaps and not production ready yet. 
Please create/upvote an [issue]([url](https://github.com/uber/cadence-charts/issues)) explaining your needs to help us prioritize.

**What is included:**
- Cadence backend services as separate deployments: frontend, history, matching, worker.
- Customizable replica counts and resource limitations.
- Customizable dynamic config as a configmap.
- A single instance ephemeral Cassandra container. This is included so that no external dependency is required to get started. Ideally you should have your own external (hosted or managed) DB instance that you can specify in values.yaml.
- The chart comes with cadence:master-auto-setup as the default image and capable of setting up Cassandra DB schema on first installation.


What is missing:
- Support for advanced visibility stores like Elasticsearch or Pinot.
- Support for persistent plugins configurations besides Cassandra.
- Support for fully customizable service config via values.yaml.
- Metrics integration with Prometheus (and more out of the box prometheus dashboards)
- Custom annotations/lables/tolerations etc.
- Support for ingress

## Usage

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```
helm repo add cadence https://cadence-workflow.github.io/cadence-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
cadence` to see the charts.

To install the cadence chart:

    helm install my-cadence cadence/cadence

To uninstall the chart:

    helm delete my-cadence

See [CONTRIBUTING.md](CONTRIBUTING.md) for instructions on how to contribute, run samples etc.

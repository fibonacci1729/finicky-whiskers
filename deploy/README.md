# Deployments

The [Finicky Whiskers](https://www.finickywhiskers.com) website is deployed via the [deploy.yaml](../.github/workflows/deploy.yml) GitHub workflow.

## Auto Deploys

The production version of the website is deployed whenever commits are pushed to the `main` branch.

## Manual Deploys

Deployments may also be [triggered manually](https://github.com/fermyon/finicky-whiskers/actions/workflows/deploy.yml), providing a choice of `ref`, `sha` and `environment` (eg canary or prod).

## Nomad jobs

We currently deploy the website via its Nomad job directly. (In the future, we envision running the website as a Fermyon Cloud app.)

The [publish-finicky-whiskers](./publish-finicky-whiskers.nomad) Nomad job checks out this repo's source code and publishes it to Bindle.

The [finicky-whiskers](./finicky-whiskers.nomad) Nomad job contains configuration for the running website, including the bindle ID to run from.
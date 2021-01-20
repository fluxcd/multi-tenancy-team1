# fluxcd-multi-tenancy-team1

## We are moving to Flux v2

> ⚠️ Please note: In preparation of [Flux v2](https://toolkit.fluxcd.io/) GA this repository with Flux v1 examples has been archived. The Flux v2 equivalent of what is shown here can be found at [flux2-multi-tenancy](https://github.com/fluxcd/flux2-multi-tenancy).
>
> Thanks a lot for your interest.

## For posterity

Demo repository for managing a multi-tenant cluster with Flux and Kustomize,
part of [fluxcd/multi-tenancy](https://github.com/fluxcd/multi-tenancy).

This repository uses [GitHub Actions](https://github.com/marketplace/actions/kubernetes-toolset)
to validate the Kubernetes manifests with kubeval and a set of Open Policy Agent
[rego rules](https://github.com/fluxcd/multi-tenancy-team1/blob/master/.github/policy/).

GitHub [workflow](https://github.com/fluxcd/multi-tenancy-team1/blob/master/.github/workflows/test.yml):
* validate kustomize build with kubeval strict mode
* deny containers with latest image tag
* deny deployments and services without app label selector
* warn if deployments have no prometheus pod annotations

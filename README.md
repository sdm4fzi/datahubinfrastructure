# SDM4FZI Datahub infrastructure

## General
For the smd4fzi datahub, 23technologies provides access to [Okeanos](https://dashboard.okeanos.dev/) which is a managed Kubernetes service based on [Gardener](gardener.cloud).
See also https://github.com/23technologies/okeanos for a general introduction.
You can login with your Github account and request access to the sdm4fzi project by contacting us via email.
Of course, it is required that you are a sdm4fzi project partner in order to get access. 

## Overview 
This repository should represent the state of the sdm4fzi datahub running on a Kubernetes cluster.
Initially, a rapid setup should be achieved by applying Kubernetes manifests into the cluster.
Eventually, [Helm](https://helm.sh/) charts should be developed and continuous deployment can be achieved by e.g. [Flux](https://fluxcd.io/).

## Getting started
Checkout the kubernetes-manifest directory and the [Readme](kubernetes-manifests/README.md) for getting started.


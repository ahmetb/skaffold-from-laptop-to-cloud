# Skaffold: From code on your laptop to cloud 💻&rarr;📦&rarr;☁️

[Skaffold](https://github.com/GoogleContainerTools/skaffold) is an open source
tool by Google that helps you build and run your source on Kubernetes locally,
or remotely on the cloud.

This repository uses [Docker's example voting app][voting] and adds Skaffold
manifest files to it and walks you through using Skaffold.

## Start your journey "from zero to Skaffold"

0. [Before you begin](00-before-you-begin/README.md)
1. [Use Skaffold to build & run apps locally on
    Minikube](10-local-build-run-with-minikube/README.md) 
1. [Use Skaffold to build & run apps locally on
    Docker for Mac/Windows](20-local-build-run-with-docker-desktop/README.md)
    
1. [Use Skaffold to build & run apps remotely
    on GKE (Google Kubernetes Engine)](30-remote-build-to-gke/README.md)
    

## Voting app architecture

![Voting app architecture
diagram](voting-app/architecture.png)

[voting]: https://github.com/dockersamples/example-voting-app


### About this tutorial

Licensed under Apache License Version 2.0. Copright 2018 Google Inc.

Author: [@ahmetb](https://twitter.com/ahmetb/)

---
title: "Running Dapr in Kubernetes with Istio"
linkTitle: "Running Dapr in Kubernetes with Istio"
weight: 100
description: >-
     Running Dapr in Kubernetes with Istio.
---

## Running Dapr in Kubernetes with Istio

Dapr can integrate with an existing Service Mesh with only a few changes required

### Deploy Istio 1.9
tbc

### Create a namespace for Dapr
kubectl create ns dapr-system

Label the namespace to enable istio-injection
kubectl label ns dapr-system istio-injection=enabled

### Install a customised version of Dapr (Using a post-renderer with Helm)
helm install dapr/dapr --post-renderer mycustomrenderer

### Create a new folder called daprcustomisations (We will use this folder to store our Kustomize patches for Dapr)
Within this folder we need to apply a few customisations, namely to the StatefulSet and Deployment manifests for dapr.



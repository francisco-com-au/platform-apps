# Platform Apps 📲

# What is this?
This is a mostly automated repo. Contains manifests to be installed by ArgoCD on clusters. This goes hand in hand with the [**Core Pipeline**](https://github.com/francisco-com-au/core-pipeline) and the the [**Platform Cluster**](https://github.com/francisco-com-au/platform-cluster) repos.

# How does this work?
- You define you Application on the [`Core Pipeline`](https://github.com/francisco-com-au/core-pipeline) repo [definitions](https://github.com/francisco-com-au/core-pipeline/tree/main/definitions)
- The [`Core Pipeline`](https://github.com/francisco-com-au/core-pipeline) (amongst other things) creates manifests here under the [`managed`](/managed/) folder to reflect the desired state of your application.
- Clusters deployed using the [`Platform Cluster`](https://github.com/francisco-com-au/platform-cluster) repo have an ArgoCD ApplicationSet watching this repo that will install anything under this pattern:
`./managed/{APP_NAME}/overlays/(dev|prod)`

# But what is that manual folder?
Currently it doesn't do anything. But the idea is that deployments that you want to handle yourself can be added here.
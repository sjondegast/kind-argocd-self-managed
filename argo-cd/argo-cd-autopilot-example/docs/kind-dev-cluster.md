# Setup Kind Development Cluster

```sh
# Create kind cluster custom name, argocd-dev. ClusterName defaults to kind
kind create cluster --name argocd-dev

# Delete kind cluster
kind delete cluster --name argocd-dev
```

https://medium.com/devopsturkiye/self-managed-argo-cd-app-of-everything-a226eb100cf0
https://medium.com/@tharukam/generate-kubernetes-manifests-with-helm-charts-using-kustomize-2f82ab5c5f11
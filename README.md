# README.md

```sh
# Start kind cluster to test, 1 master + 3x worker nodes
# Kind Configuration: tools/kind-cluster/kind-config.yaml

# Create Cluster
kind create cluster --config ./kind-config.yaml

# Delete Cluster
kind delete cluster
```

## Run ArgoCD bootstrap

```sh
# CD into argo-self-managed/bootstrap/argo-cd from project root
cd argo-self-managed/bootstrap/argo-cd

# Use kubectl with kustomize to deploy argoCD from inside the directory
kubectl apply -k .

# CD into bootstrap directory: argo-self-managed/bootstrap from project root
cd argo-self-managed/bootstrap

# Apply argoCD CRD projects, applications incl argoCD application
kubectl apply -f . # This will not pickup the folders inside that directory
```

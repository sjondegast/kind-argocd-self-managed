# README.md

## Setup Development Cluster with Kind

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

## Best Practices

- https://argo-cd.readthedocs.io/en/stable/user-guide/best_practices/
- [Separating Config Vs. Source Code Repositories](https://argo-cd.readthedocs.io/en/stable/user-guide/best_practices/#separating-config-vs-source-code-repositories)

## Helm

- https://argo-cd.readthedocs.io/en/stable/user-guide/helm/

## ApplicationSet

- https://argo-cd.readthedocs.io/en/stable/user-guide/application-set/

## Plugins

- https://argo-cd.readthedocs.io/en/stable/operator-manual/config-management-plugins/

## TODO

- https://redhat-scholars.github.io/argocd-tutorial/argocd-tutorial/index.html
- https://redhat-scholars.github.io/argocd-tutorial/argocd-tutorial/04-syncwaves-hooks.html
- https://argo-cd.readthedocs.io/en/stable/operator-manual/app-any-namespace/
- https://argo-cd.readthedocs.io/en/stable/operator-manual/reconcile/#reconcile-optimization
- https://argo-cd.readthedocs.io/en/stable/operator-manual/webhook/

## Resources

- https://medium.com/@aaltundemir/demystifying-gitops-bootstrapping-argo-cd-4a861284f273
- https://medium.com/devopsturkiye/self-managed-argo-cd-app-of-everything-a226eb100cf0
- https://ahmedelfakharany.com/combining-helm-and-kustomize-when-why-and-how-96a3483310db
- https://fluxcd.io/flux/guides/repository-structure/
- https://github.com/fluxcd/flux2-kustomize-helm-example/tree/main
- https://github.com/argoproj/argoproj-deployments/blob/master/argocd/kustomization.yaml
- https://cloudogu.com/en/blog/gitops-repository-patterns-part-6-examples
- https://cloudogu.com/en/blog/gitops-repository-patterns-part-3-repository-patterns#monorepo
- https://github.com/PacktPublishing/Modern-DevOps-Practices-2e/blob/main/ch12/environments-argocd-app/manifests/argocd/apps.yaml
- https://argo-cd.readthedocs.io/en/stable/operator-manual/cluster-bootstrapping/
- https://github.com/redhat-scholars/argocd-tutorial.git
- https://www.redhat.com/en/topics/devops/what-is-gitops
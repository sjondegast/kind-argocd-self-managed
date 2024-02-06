# TASKS

- [x] Test if updating argoCD using self managed argocd application.yaml works.
`argo-self-managed/bootstrap/argo-cd/kustomization.yaml`
- [x] Create application.yaml file for projects folder to automatically pick up all projects in that folder: `argo-self-managed/bootstrap/argocd-projects.yaml`
- [ ] Add multiple applications, diff kinds of resources from the argo-cd repo: `https://github.com/argoproj/argocd-example-apps.git`
- [ ] Add multiple projects and test multiple applications in context with that project
- [ ] Refactor Current Setup
  - [ ] Restructure kustomizations inside `argo-self-managed/bootstrap/argo-cd` folder, using `patches/` and `resources/`.
- [ ] [Setup ArgoCD argocd-image-updater](https://github.com/argoproj-labs/argocd-image-updater/blob/master/docs/install/installation.md)
- [ ] Configure ArgoCD using configmaps, values set via helm charts/values.yaml but using kustomized installation
- [ ] Create secrets for gitlab and link it using token
- [ ] Design argo-cd setup using openshift docs and github example repo
- [ ] argo-cd argocd-notifications-cm
<!-- - [ ] https://github.com/PacktPublishing/ArgoCD-in-Practice/blob/main/ch04/kustomize-installation/argocd-app.yaml -->
## Research how to refactor argocd kustomization setup

- [example argocd](https://github.com/argoproj/argoproj-deployments/tree/master/argoproj)

## Features

### kustomize: components?

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

namespace: argocd

resources:
- base/argo-cd-issuer.yaml
- base/argo-cd-certificate.yaml
- base/argo-cd-ui-ingress.yaml
- base/jenkins-ingress.yaml
- base/rollouts-extension.yaml
- https://raw.githubusercontent.com/argoproj/argo-cd/master/manifests/ha/install.yaml

components:
- https://github.com/argoproj-labs/argocd-extensions/manifests

patchesStrategicMerge:
- overlays/production/argo-cd-cm.yaml
- overlays/production/argocd-server-service.yaml
- overlays/production/argocd-repo-server-deploy.yaml
- overlays/production/argocd-notifications-controller-deploy.yaml
- overlays/production/argocd-notifications-cm.yaml
- overlays/production/argocd-cmd-params-cm.yaml
- https://raw.githubusercontent.com/argoproj/argo-cd/master/notifications_catalog/install.yaml

images:
- name: quay.io/argoproj/argocd
  newName: ghcr.io/argoproj/argo-cd/argocd
  newTag: 2.9.0-5246429c
```
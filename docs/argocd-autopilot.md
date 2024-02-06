# Argo-CD Autopilot

New users to GitOps and Argo CD are not often sure how they should structure their repos, add applications, promote apps across environments, and manage the Argo CD installation itself using GitOps.

- [Argo-CD Autopilot docs](https://argocd-autopilot.readthedocs.io/en/stable/)
- [Argo-CD bootstrap example github](https://github.com/a1tan/testautopilot/tree/main/bootstrap)

## Installation

### Using brew

```sh
# install
brew install argocd-autopilot

# check the installation
argocd-autopilot version
```

## Using a Specific git Provider

You can add the --provider flag to the repo bootstrap command, to enforce using a specific provider when creating a new repository. If the value is not supplied, the code will attempt to infer it from the clone URL.

Autopilot currently supports a variety of git providers, you should check if yours is currently supported here.

### Git Providers

Autopilot fully automates the installation process and bootstrapping of Argo CD, it can even create and initialize a git repository if required, but to do so it needs to have access to your git provider.

The following git providers are currently supported:

- Github
- Gitlab
- Bitbucket Server (on-prem only)
- Azure DevOps
- Gitea

## Bootstrap Argo-CD

### Create Git token GitHub

1. navigate to github [repo/developer-settings](https://github.com/settings/apps)
2. navigate to personal access token, select classic token or the alternative fined graned token.
3. select box repo: Full control of private repositories

```sh
export GIT_TOKEN=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

# argocd-autopilot repo bootstrap --repo https://github.com/example/repo
argocd-autopilot repo bootstrap --repo https://github.com/sjondegast/kind-argocd-self-managed.git
```

## bootstrap argo-cd kustomization

https://github.com/argoproj-labs/argocd-autopilot/tree/main/manifests

github.com/argoproj-labs/argocd-autopilot/manifests/base

https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
https://github.com/argoproj/argo-cd/blob/stable/manifests/install.yaml
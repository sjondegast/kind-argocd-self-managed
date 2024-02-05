# GitOps Directory and Git Structures

- [source](https://developers.redhat.com/articles/2022/09/07/how-set-your-gitops-directory-structure#directory_structures)

## Directory structures

### Kubernetes platform administrator

```sh
├── bootstrap

│   ├── base

│   └── overlays

│       └── default

├── cluster-config

│   ├── gitops-controller

│   ├── identity-provider

│   └── image-scanner

└── components

    ├── applicationsets

    ├── applications

    └── argocdproj
```

### Kubernetes application developer

```sh
└── deploy

    ├── base

    └── overlays

        ├── dev

        ├── prod

        └── stage
```

## GitOps repo example

```sh
├── bootstrap

│   ├── base

│   └── overlays

│       └── default

├── components

│   ├── applicationsets

│   └── argocdproj

├── core

│   ├── gitops-controller

│   └── sample-admin-workload

└── apps

      ├── bgd-blue

      │   ├── base

      │   └── overlays

      │       ├── dev

      │       ├── prod

      │       └── stage

      └── myapp

          ├── base

         └── overlays

           ├── dev

           ├── prod

           └── stage
```

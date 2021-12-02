# actions-library
Github Actions used within this org


## Reusable Worklows
[Github Documentation](https://docs.github.com/en/actions/learn-github-actions/reusing-workflows)

### build-and-deploy-container-image
Build and deploy a container image build with yarn. It combines composites 
* build-docker-image
* check-code-compliance
* deploy-pr
* semantic-release

### delete-pr-deployment
Deletes a PR Deployment for a service repository which has been created by  `build-and-deploy-container-image`

### release-docker-image
Tags an existing Docker Image with the released tag.

### gitops-create-pr-deployment
Verifies output of `kustomization` and creates a deployment based on an existing ArgoCD App

### gitops-delete-pr-deployment
Deletes a deployment being created with `gitops-create-pr-deployment`


## Composites
[Github Documentation](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)

### build-docker-image
Builds and pushes a docker image

### check-code-compliance
Checks licenses of used dependencies against a list of allowed licenses

### deploy-pr
Deploys this PRs created container image on a cluster managed by ArgoCD

### release-docker-image
Tags an already built docker image with a release tag

### semantic-release
| Deprecated: use reusable workflow `release-docker-image` instead

Creates a semantic release

# helm

This repository contains Helm charts used for deploying applications to a Kubernetes cluster. Currently, it includes the mychart Helm chart, which is a template for deploying a Java application.


## Repository Structure

```plaintext
my-helm-repo/
│
├── mychart/
│   ├── charts/
│   ├── templates/
│   ├── Chart.yaml
│   ├── values.yaml
│   └── README.md
└── index.yaml


- **mychart/**: Contains the Helm chart files for the application.

 - **charts/**: Directory for dependent charts.
 - **templates/**: Contains Kubernetes manifests that Helm uses to generate the final Kubernetes  resource files.
 - **Chart.yaml**: Metadata about the chart (name, version, description).
 - **values.yaml**: Default configuration values for the chart.
 - **README.md**: Documentation for the chart (optional).
- **index.yaml**: The Helm repository index file listing all available charts.

## Setup

1. **Add the Helm Repository:**
`helm repo add myHelmRepo https://helm-18bc38.gitlab.io/my-helm-repo/
 helm repo update
`

2. **Install the Chart:**
`helm install myapp myHelmRepo/mychart
`

3. **Upgrade the Chart:**
`helm upgrade myapp myHelmRepo/mychart
`

4. **Uninstall the Chart:**
`helm uninstall myapp
`

## How to Update the Chart


1. Make Changes: Update files in the mychart/ directory as needed (e.g., values.yaml, templates).

2. Package the Chart:

`helm package mychart
`

3. Update the Index File:

`helm repo index . --url https://helm-18bc38.gitlab.io/my-helm-repo/
`

4. Push Changes: Commit and push changes to the repository.



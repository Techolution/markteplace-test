# appmod-pa-demo Marketplace Package

This repository contains everything needed to package **appmod-pa-demo** as a Kubernetes & Anthos App on Google Cloud Marketplace.

## Contents

- **chart/templ/** – Helm chart for appmod-pa-demo  
- **schema.yaml** – JSON Schema driving the Marketplace UI  
- **Dockerfile** – Deployer image (Helm onbuild) with Marketplace annotations  
- **LICENSE** – Apache 2.0 license  

## Prerequisites

- Google Cloud SDK & Artifact Registry enabled  
- `mpdev` CLI installed (see [tool-prerequisites](https://github.com/GoogleCloudPlatform/marketplace-k8s-app-tools))  
- A GKE cluster for testing  

## Local Testing

1. **Build & push** your deployer image:
   ```bash
   export REG=us-docker.pkg.dev/techolution-public/appmod-pa-demo
   docker build -t $REG/deployer:1.0 .
   docker push $REG/deployer:1.0

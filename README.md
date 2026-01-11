# spring-aca-demo

Simple Spring Boot app deployed to Azure Container Apps using GitHub Actions.

## Local run

```bash
mvn spring-boot:run
```

## GitHub Actions deploy to ACA

### 1) Create Azure resources (one-time)

- Create a resource group
- Create an Azure Container Apps environment
- Create an Azure Container Registry (ACR)
- Create a Container App

### 2) Create a service principal and save GitHub secrets

Create a service principal with access to the resource group and save its JSON output as `AZURE_CREDENTIALS`.
Also add these secrets in your GitHub repo:

- `AZURE_RESOURCE_GROUP`
- `AZURE_CONTAINERAPPS_ENVIRONMENT`
- `AZURE_CONTAINERAPP_NAME`
- `AZURE_CONTAINER_REGISTRY`
- `AZURE_CREDENTIALS`

### 3) Push to main

A push to `main` triggers the workflow and deploys the container image to ACA.

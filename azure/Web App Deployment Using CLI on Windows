# Azure Deployment Process

## Prerequisites

- Ensure you have an Azure subscription.
- Azure CLI installed and configured on your Windows machine.
- Visual Studio or a ZIP file of your application for deployment.

## Steps

### 1. Create a Resource Group

To create a new resource group named `practicas` in the "Central Mexico" region:

az group create --name practicas --location "Central Mexico"

### 2. Create a Resource Group
Before creating App Service resources, you need to register the resource provider:
az provider register --namespace Microsoft.Web

### 3. Create an App Service Plan
Create an App Service Plan named cafebit with the Basic tier (SKU B1):
az appservice plan create --name cafebit --resource-group practicas --location "Central Mexico" --sku B1

### 4. Create an App Service
Create an App Service named cafebit with the .NET 6 runtime:
az webapp create --resource-group practicas --plan cafebit --name cafebit --runtime "DOTNET|6.0"

### 5. Deploy Your Application
Using Visual Studio
Open Visual Studio and right-click on your project.
Select "Publish".
Choose "Azure" as the target.
Select your App Service (cafebit) and follow the steps to complete the publishing process.

Using Azure CLI (ZIP Deployment)
If you have your application packaged as a ZIP file, deploy it using the following command:
az webapp deployment source config-zip --resource-group practicas --name cafebit --src <path_to_your_zip_file>

---
title: 'Quickstart: Deploy Azure API for FHIR using Azure CLI'
description: In this quickstart, you'll learn how to deploy Azure API for FHIR in Azure using the Azure CLI.
services: healthcare-apis
author: matjazl
ms.service: healthcare-apis
ms.subservice: fhir
ms.topic: quickstart
ms.date: 10/15/2019
ms.author: zxue
ms.custom: devx-track-azurecli, mode-api
---

# Quickstart: Deploy Azure API for FHIR using Azure CLI

In this quickstart, you'll learn how to deploy Azure API for FHIR in Azure using the Azure CLI.

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [azure-cli-prepare-your-environment.md](../../../includes/azure-cli-prepare-your-environment.md)]

## Add HealthcareAPIs extension

```azurecli-interactive
az extension add --name healthcareapis
```

Get a list of commands for HealthcareAPIs:

```azurecli-interactive
az healthcareapis --help
```

## Create Azure Resource Group

Pick a name for the resource group that will contain the Azure API for FHIR and create it:

```azurecli-interactive
az group create --name "myResourceGroup" --location westus2
```

## Deploy the Azure API for FHIR

```azurecli-interactive
az healthcareapis create --resource-group myResourceGroup --name nameoffhiraccount --kind fhir-r4 --location westus2 
```

## Fetch FHIR API capability statement

Obtain a capability statement from the FHIR API with:

```azurecli-interactive
curl --url "https://nameoffhiraccount.azurehealthcareapis.com/metadata"
```

## Clean up resources

If you're not going to continue to use this application, delete the resource group with the following steps:

```azurecli-interactive
az group delete --name "myResourceGroup"
```

## Next steps

In this quickstart guide, you've deployed the Azure API for FHIR into your subscription. To set additional settings in your Azure API for FHIR, proceed to the additional settings how-to guide. If you are ready to start using the Azure API for FHIR, read more on how to register applications.

>[!div class="nextstepaction"]
>[Additional settings in Azure API for FHIR](azure-api-for-fhir-additional-settings.md)

>[!div class="nextstepaction"]
>[Register Applications Overview](fhir-app-registration.md)

---
title: Route traffic for HA of applications - Azure CLI - Traffic Manager
description: Azure CLI script sample - Route traffic for high availability of applications
services: traffic-manager
documentationcenter: traffic-manager
author: asudbring
manager: twooley

tags: azure-infrastructure

ms.assetid:
ms.service: traffic-manager
ms.devlang: azurecli
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: traffic-manager
ms.date: 04/26/2018
ms.author: allensu
---

# Route traffic for high availability of applications using Azure CLI

This script creates a resource group, two app service plans, two web apps, a traffic manager profile, and two traffic manager endpoints. Traffic Manager directs traffic to the application in one region as the primary region, and to the secondary region when the application in the primary region is unavailable. Before executing the script, you must change the MyWebApp, MyWebAppL1 and MyWebAppL2 values to unique values across Azure. After running the script, you can access the app in the primary region with the URL mywebapp.trafficmanager.net.

[!INCLUDE [sample-cli-install](../../../includes/sample-cli-install.md)]

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

## Sample script

[!code-azurecli-interactive[main](../../../cli_scripts/traffic-manager/direct-traffic-for-increased-application-availability/direct-traffic-for-increased-application-availability.sh "Route traffic for high availability")]


## Clean up deployment 

After the script sample has been run, the follow command can be used to remove the resource group, App Service app, and all related resources.

```azurecli
az group delete --name myResourceGroup1 --yes
az group delete --name myResourceGroup2 --yes
```

## Script explanation

This script uses the following commands to create a resource group, web app, traffic manager profile, and all related resources. Each command in the table links to command specific documentation.

| Command | Notes |
|---|---|
| [az group create](/cli/azure/group) | Creates a resource group in which all resources are stored. |
| [az appservice plan create](/cli/azure/appservice/plan) | Creates an App Service plan. This is like a server farm for your Azure web app. |
| [az webapp web create](/cli/azure/webapp#az_webapp_create) | Creates an Azure web app within the App Service plan. |
| [az network traffic-manager profile create](/cli/azure/network/traffic-manager/profile) | Creates an Azure Traffic Manager profile. |
| [az network traffic-manager endpoint create](/cli/azure/network/traffic-manager/endpoint) | Adds an endpoint to an Azure Traffic Manager Profile. |

## Next steps

For more information on the Azure CLI, see [Azure CLI documentation](/cli/azure).

Additional App Service CLI script samples can be found in the [Azure Networking documentation](../cli-samples.md).
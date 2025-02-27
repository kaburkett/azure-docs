---
title: Add regions, change failover priority, trigger failover for an Azure Cosmos account
description: Add regions, change failover priority, trigger failover for an Azure Cosmos account
author: markjbrown
ms.author: mjbrown
ms.service: cosmos-db
ms.topic: sample
ms.date: 02/21/2022
---

# Add regions, change failover priority, trigger failover for an Azure Cosmos account using Azure CLI

[!INCLUDE[appliesto-all-apis](../../../includes/appliesto-all-apis.md)]

The script in this article demonstrates three operations.

- Add a region to an existing Azure Cosmos account.
- Change regional failover priority (applies to accounts using automatic failover)
- Trigger a manual failover from primary to secondary regions (applies to accounts with manual failover)

This script uses a SQL (Core) API account, but these operations are identical across all database APIs in Cosmos DB.

> [!IMPORTANT]
> Add and remove region operations on a Cosmos account cannot be done while changing other properties.

[!INCLUDE [quickstarts-free-trial-note](../../../../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [azure-cli-prepare-your-environment.md](../../../../../includes/azure-cli-prepare-your-environment.md)]

- This article requires version 2.9.1 or later of the Azure CLI. If using Azure Cloud Shell, the latest version is already installed.

## Sample script

[!INCLUDE [cli-launch-cloud-shell-sign-in.md](../../../../../includes/cli-launch-cloud-shell-sign-in.md)]

### Run the script

:::code language="azurecli" source="~/azure_cli_scripts/cosmosdb/common/regions.sh" range="4-32":::

## Clean up resources

[!INCLUDE [cli-clean-up-resources.md](../../../../../includes/cli-clean-up-resources.md)]

```azurecli
az group delete --name $resourceGroup
```

## Sample reference

This script uses the following commands. Each command in the table links to command specific documentation.

| Command | Notes |
|---|---|
| [az group create](/cli/azure/group#az_group_create) | Creates a resource group in which all resources are stored. |
| [az cosmosdb create](/cli/azure/cosmosdb#az_cosmosdb_create) | Creates an Azure Cosmos DB account. |
| [az cosmosdb update](/cli/azure/cosmosdb#az_cosmosdb_update) | Updates an Azure Cosmos DB account (add or remove region). |
| [az cosmosdb failover-priority-change](/cli/azure/cosmosdb#az_cosmosdb_failover_priority_change) | Update failover priority or trigger failover on an Azure Cosmos DB account. |
| [az group delete](/cli/azure/resource#az_resource_delete) | Deletes a resource group including all nested resources. |

## Next steps

For more information on the Azure Cosmos DB CLI, see [Azure Cosmos DB CLI documentation](/cli/azure/cosmosdb).

For Azure CLI samples for specific APIs see:

- [CLI Samples for Cassandra](../../../cassandra/cli-samples.md)
- [CLI Samples for Gremlin](../../../graph/cli-samples.md)
- [CLI Samples for MongoDB API](../../../mongodb/cli-samples.md)
- [CLI Samples for SQL](../../../sql/cli-samples.md)
- [CLI Samples for Table](../../../table/cli-samples.md)

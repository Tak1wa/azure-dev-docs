---
title: Clean up resources after deploying a containerized Node.js app from Visual Studio Code
description: Docker Tutorial part 8, clean up resources
ms.topic: how-to
ms.date: 08/17/2021
ms.custom: devx-track-js
---

# 8. Clean up resources

Remove the Azure Container registry and the App service by removing the resource group which contains them.

## Delete resource group

The App Service you created for the container includes a backing App Service Plan that can incur costs. Use the Visual Studio Code extension, Azure Resource Groups, to delete the resource group and all resources within the group.

1. Find the resource group name in the list.
1. Right-click the resource group name and select **Delete**.

    :::image type="content" source="../../media/visual-studio-code-azure-resources-extension-remove-resource-group.png" alt-text="Use the Visual Studio Code extension, Azure Resource Groups, to delete the resource group and all resources within the group.":::

## Next steps

[!INCLUDE [tutorial-next-steps](../../includes/tutorial-next-steps.md)]

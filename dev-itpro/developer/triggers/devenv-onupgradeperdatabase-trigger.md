---
title: "OnUpgradePerDatabase Trigger"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: blrobl
---

# OnUpgradePerDatabase Trigger
Runs during the upgrade of an extension.

## Applies To  
-  Upgrade codeunits. These codeunits have the [SubType Property \(Codeunit\)](../properties/devenv-subtype-property-codeunit.md) set to **Upgrade**.  

> [!NOTE]  
>  This trigger is also available in upgrade codeunits for the base application, not just for extensions.  

## Remarks  
It is used to perform the actual upgrade. If an error occurs during runtime the extension upgrade is canceled.

This trigger is run once in the entire upgrade process, in a single system session that does not open any company.

## See Also  
 [Triggers](devenv-triggers.md)  
 [Codeunit Triggers](devenv-codeunit-triggers.md)  
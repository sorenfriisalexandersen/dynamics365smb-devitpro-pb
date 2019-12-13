---
title: "OnAfterModify Trigger"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: solsen
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: t-blrobl
ms.service: "dynamics365-business-central"
author: blrobl
---

# OnAfterModify Trigger
Runs when a user modifies an existing record in a table.  
  
## Applies To  
- Table extensions
  
## Remarks  
 This trigger is run after the default modify behavior, which checks that all the fields of a record are valid before the modification occurs. It runs automatically when the user changes at least one field (different from the primary key field) of a record in a page from the Web Client. If an error occurs in the trigger code, the record changes are canceled.  
  
## See Also  
 [Triggers](devenv-triggers.md)  
 [Table and Field Triggers](devenv-table-and-field-triggers.md)  
 [OnBeforeModify Trigger](devenv-onbeforemodify-trigger.md)

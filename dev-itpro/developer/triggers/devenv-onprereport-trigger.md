---
title: "OnPreReport Trigger"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# OnPreReport Trigger
Runs before a report is run.  

## Syntax  
```  
trigger OnPreReport() 
begin
    ...
end;
``` 
 
## Applies To  
- Reports  
  
## Remarks  
 This trigger runs after the request page is run. The table views and filters for the report data items are set while this trigger is run. As this trigger is run after the request page is processed, you have access to any filters the user has set. If you want to print the settings of these filters in the report, you can retrieve them using the following text string.  
  
```  
ReportFilter := SomeRecord.GETFILTERS;  
```  
  
 Use the ReportFilter text string as the source expression for a control in a section of the report.  
  
## See Also  
 [Triggers](devenv-triggers.md)  
 [GETFILTERS Method Record](../methods/devenv-getfilters-method-record.md)  
 [Report and Data Item Triggers](devenv-report-and-data-item-triggers.md)  
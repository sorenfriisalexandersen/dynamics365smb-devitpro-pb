---
title: "OnPostReport Trigger"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# OnPostReport Trigger
Runs after a report is run.  

## Syntax  
```  
trigger OnPostReport()
begin
    ...
end;
``` 

## Applies To  
- Reports  

## Remarks  
 This trigger is run after all data items are processed. The trigger is not run if the report was stopped manually or by using the QUIT  before processing had concluded.  

 Because this trigger is run after the report is processed, you can use it to inform users about the result of the report run. For example, if some records could not be processed, you could inform the user of this using the following code in this trigger.  

```  
if ProblemsInReport then  
MESSAGE(Text000, NumberOfErrors);  
```  

 Create the following global text constant variable.  

|**Text constant**|**ENU value**|  
|-----------------------|-------------------|  
|Text000|'%1 records were not processed'|  

 Because this trigger is run before the End Write Transaction, you can also give the user the opportunity to roll back changes to the database by leaving the report with the [QUIT Method \(Report, XMLport\)](../methods/devenv-quit-method-report-xmlport.md).  

## See Also  
 [Triggers](devenv-triggers.md)  
 [QUIT Method (Report, XMLport)](../methods/devenv-quit-method-report-xmlport.md)  
 [Report and Data Item Triggers](devenv-report-and-data-item-triggers.md)  

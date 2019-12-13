---
title: "SourceTableView Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: 3b99a282-bc11-471c-928c-3b305d94a900
caps.latest.revision: 8
author: SusanneWindfeldPedersen
---

# SourceTableView Property
Sets the key, sort order, and filter you want to use to determine the view of the source table presented to the user.  
  
## Applies To  
  
-   Pages  

## Example

```
page 50101 MyCustomers
{
    PageType = List;
    SourceTable = Customer;
    SourceTableView = sorting (Name) order(descending)
 where ("Balance (LCY)" = filter (>= 50000), "Sales (LCY)" = filter (<> 0));
    layout
    {
        area(Content)
        {
            repeater(MyRepeater)
            {
                field(Name; Name) { }
                field(Address; Address) { }
                field("Balance (LCY)"; "Balance (LCY)") { }
            }
        }
    }
}
```

For more information on how you can scan, find, and limit records in a list, see [Sorting, Searching, and Filtering Lists](/dynamics365/business-central/ui-enter-criteria-filters). 
  
## See Also  
 [Properties](devenv-properties.md)
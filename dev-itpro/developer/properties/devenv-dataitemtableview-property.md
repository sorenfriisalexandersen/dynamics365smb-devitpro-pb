---
title: "DataItemTableView Property"

ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# DataItemTableView Property
Sets the key on which to sort, the sort order, and the filters for the data item.  
  
## Applies To  
Data items on reports.  

## Examples

In the following example, the **DataItemView** property is used to sort a table view based on the `"Entry No."` field.
```
DataItemTableView = SORTING ("Entry No.");
```
This code sample shows how the same property can be used to apply filters on a table view.
```
DataItemTableView = WHERE("Document Type" = FILTER(Payment | Invoice | "Credit Memo"), Open= CONST(true));
```
  
## Remarks  
 
- If you set a key, then the data item does not have a FastTab on the request page and the end users cannot select a key for sorting, sort order, or filters for the data item.  
  
- If you set a sort order, then this sort order is used for the report, regardless of the sort order that the end user selects on the request page.  
  
- If you set a filter, then this filter is not displayed on the request page but it is used along with any filters that the end user specifies on the request page.  
  
- Setting a sort order, a filter, or both does not prevent end users from selecting a sort field on the request page. The default sort field that is displayed in the request page is the primary key. The list of fields on which you can sort includes all keys for the data item. To add fields to the list, you must add keys to the table.

## See Also  
[Request Pages](../devenv-request-pages.md)
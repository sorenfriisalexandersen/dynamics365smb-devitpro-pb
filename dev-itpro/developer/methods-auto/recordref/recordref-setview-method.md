---
title: "SetView Method"
ms.author: solsen
ms.custom: na
ms.date: 10/09/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---
[//]: # (START>DO_NOT_EDIT)
[//]: # (IMPORTANT:Do not edit any of the content between here and the END>DO_NOT_EDIT.)
[//]: # (Any modifications should be made in the .xml files in the ModernDev repo.)
# SetView Method
Sets the current sort order, key, and filters on a table.


## Syntax
```
 RecordRef.SetView(String: String)
```
## Parameters
*RecordRef*  
&emsp;Type: [RecordRef](recordref-data-type.md)  
An instance of the [RecordRef](recordref-data-type.md) data type.  

*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The string format is the same as the SourceTableView property on pages.  



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The value of the *String* parameter can be returned by the [GETVIEW Method \(RecordRef\)](recordref-getview-method.md).  
  
 If the SETVIEW method is executed with an empty string, all the filters are removed and the primary key is used.  
  
 If no table is selected, the SETVIEW method fails.  
  
 This method works the same as the [SETVIEW Method \(Record\)](../record/record-setview-method.md).  
  
## Example  
 The following example opens the Customer \(18\) table as a RecordRef variable that is named CustomerRecRef. The SETVIEW method sets the sort key to the Name field, sort order to Ascending and sets a filter that selects records between 1000 and 2000. The [GETVIEW Method \(RecordRef\)](recordref-getview-method.md) retrieves the sort order, key and filters that have been set and stores the value in the ViewString variable. The value in the ViewString variable is displayed in a message box. 

```  
var
    CustomerRecRef: RecordRef;
    ViewString: Text;
    Text000: Label 'The following is the current sort order, key, and filters that are set: %1';
begin   
    CustomerRecRef.OPEN(18);  
    CustomerRecRef.SETVIEW('SORTING(Name) ORDER(Ascending) WHERE(No.=CONST(10000..20000))');  
    ViewString := CustomerRecRef.GETVIEW;  
    MESSAGE(Text000, ViewString);  
end;
  
```  

## See Also
[RecordRef Data Type](recordref-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
---
title: "Variant2Time Method"
ms.author: solsen
ms.custom: na
ms.date: 10/01/2019
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
# Variant2Time Method
Gets a time from a variant.


## Syntax
```
Time :=   System.Variant2Time(Variant: Variant)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Variant*  
&emsp;Type: [Variant](../variant/variant-data-type.md)  
The input variant.  


## Return Value
*Time*  
&emsp;Type: [Time](../time/time-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
```  
var
    TextTime: Time;
    variant1: Variant;
begin 
    variant1 := TIME;  
    TestTime := VARIANT2TIME(variant1);  
end;
```  


## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
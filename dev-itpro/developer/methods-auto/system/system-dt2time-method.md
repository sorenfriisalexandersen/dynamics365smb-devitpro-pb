---
title: "DT2Time Method"
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
# DT2Time Method
Gets the time part of a DateTime object.


## Syntax
```
Time :=   System.DT2Time(Datetime: DateTime)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Datetime*  
&emsp;Type: [DateTime](../datetime/datetime-data-type.md)  
The DateTime of which to return the time part.  


## Return Value
*Time*  
&emsp;Type: [Time](../time/time-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 If *Datetime* is undefined, then this method returns an undefined time.

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
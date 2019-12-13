---
title: "CanLoadType Method"
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
# CanLoadType Method
Tests if the specified .NET Framework type can be loaded.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
Ok :=   System.CanLoadType(DotNet: DotNet)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*DotNet*  
&emsp;Type: [DotNet](../dotnet/dotnet-data-type.md)  
A variable of the DotNet data type to represent the .NET Framework type.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The following code example is based on codeunit 5300 in the [!INCLUDE[demolong](../../includes/demolong_md.md)]. 

```
var
    OObjLibrary: DotNet "Microsoft.Dynamics.NAV.OLSync.OLSyncSupplier.OutlookObjectLibrary.'Microsoft.Dynamics.NAV.OLSync.OLSyncSupplier, Version=7.1.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'";
    MyError: Label 'Cannot access the specified type.';
if not CANLOADTYPE(OObjLibrary) then  
   ERROR(MyError);  
```  

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
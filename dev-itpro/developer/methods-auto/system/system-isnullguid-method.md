---
title: "IsNullGuid Method"
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
# IsNullGuid Method
Indicates whether a value has been assigned to a GUID. A null GUID that consists only of zeros is valid but must never be used for references.


## Syntax
```
Ok :=   System.IsNullGuid(Guid: Guid)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Guid*  
&emsp;Type: [Guid](../guid/guid-data-type.md)  
The GUID that you want to check whether it is null.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 The GUID data type is useful when you want to uniquely identify data so that it can be exchanged with external applications. For example, if you want to transfer an item catalog to an external application, you add a GUID field to the record in the table and use it as the primary reference when you communicate with the external application. A GUID is a 16-byte binary data type that can be logically grouped into the following subgroups: 4byte-2byte-2byte-2byte-6byte.  
  
## Example  
 The following example initializes two variables named validGuid and nullGuid. The validGuid variable is assigned a valid GUID value, and the nullGuid variable is assigned a null GUID that consists of only zeros. The ISNULLGUID method determines whether the GUID that is contained in the *validGuid* parameter is null. In this case, the GUID is not null so a message that states that the GUID is not null is displayed and the value is displayed. The method then checks the *nullGuid* parameter. This time, a message that states that the GUID is null is displayed because the GUID is a null GUID that consists of only zeros. 
 
```  
var
    validGuid: GUID;
    nullGuid: GUID;
    Text000: Label 'The GUID is null';
    Text0001: Label 'The GUID is not null.\\';
    Text0002: Label 'The value is %1.';
begin
    validGuid := '{FC841BE6-0ADA-46C4-A6A9-142AEC211613}';  
    nullGuid  := '{00000000-0000-0000-0000-000000000000}';        
    if ISNULLGUID(validGuid) then  
      MESSAGE(Text000)  
    else   
      MESSAGE(Text001 + Text002, validGuid);  
    if ISNULLGUID(nullGuid) then  
      MESSAGE(Text000);  
end;
```  
  

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
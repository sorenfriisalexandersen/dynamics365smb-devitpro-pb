---
title: "GetLastErrorObject Method"
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
# GetLastErrorObject Method
Gets the last System.Exception object that occurred.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
DotNet :=   System.GetLastErrorObject()
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*DotNet*  
&emsp;Type: [DotNet](../dotnet/dotnet-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)


## Remarks  
 You use this method to retrieve and handle the last exception that occurred in the application. The System.Exception object exposes several members that enable you to get detailed information about the exception, such Exception.InnerException and Exception.Message.  
  
## Example  
 This example uses the GETLASTERROROBJECT method to get an exception object that occurs. In this example, the Microsoft .NET Framework objects are executed by MyCodeunit. The AL code uses the InnerException property of the System.Exception object to identify whether the inner exception has the type WebException and returns an exception message accordingly.  
  
  
```  
var
    MyCodeunit: Codeunit MyCodeunit;
    Exception: DotNet "'System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'.System.Net.WebException";
    WebException: DotNet "'mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'.System.Exception";
begin
    if not MyCodeunit.RUN then begin  
        Exception := GETLASTERROROBJECT;  
      
        if not Exception.InnerException.GetType.Equals(WebException.GetType) then  
            ERROR(Exception.Message);  
      
        WebException := Exception.InnerException;  
        ERROR(WebException.Message);  
    end;  
end;
```  
## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
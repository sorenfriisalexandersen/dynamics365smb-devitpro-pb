---
title: "Today Method"
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
# Today Method
Gets the current date set in the operating system.


## Syntax
```
Date :=   System.Today()
```
> [!NOTE]  
> This method can be invoked using property access syntax.  
> [!NOTE]  
> This method can be invoked without specifying the data type name.  


## Return Value
*Date*  
&emsp;Type: [Date](../date/date-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  

The date that is returned is different for the [!INCLUDE[webclient](../../includes/webclient.md)] and [!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]. For the Web client, the day is determined by the Regional Setting that is set under **MySetting** in the client. The very first time a user signs in, the system automatically determines the Regional Setting based on the user's browser/computer. For the Windows client, TODAY returns the current day of the computer that is running the client, as determined by the date and time settings of the operating system.

You can only use the **TODAY** method to retrieve the current date from the operating system. You cannot use it to set the date in the operating system.  
  
## Example  
 This example shows how to use the **TODAY** method. 
 
```  
var
    Text000: Label 'The current date is: %1';
begin
    MESSAGE(Text000, TODAY);  
end;
```  
  
 The message window could display the following:  
  
 **The current date is: 05/27/08**  
  

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
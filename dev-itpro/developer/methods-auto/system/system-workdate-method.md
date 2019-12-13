---
title: "WorkDate Method"
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
# WorkDate Method
Gets and sets the work date for the current session.


## Syntax
```
[WorkDate := ]  System.WorkDate([NewDate: Date])
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*NewDate*  
&emsp;Type: [Date](../date/date-data-type.md)  
The new work date you want to set.  


## Return Value
*WorkDate*  
&emsp;Type: [Date](../date/date-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
<!--NAV
If you do not set a value for the *NewDate* parameter, then the method returns the work date that is specified by the **Set Work Date** option on the **Application** menu ![Application Menu button in menu bar](media/ApplicationMenuIcon.png "ApplicationMenuIcon") in the [!INCLUDE[nav_windows](../includes/nav_windows_md.md)]. If there is no work date selected,  then the current system date is returned.  
-->

 To set the work date to follow the calendar day so that the work date is always the current date, set *NewDate* to `TODAY` or `0D`. If you explicitly set *NewDate* to the current date, then the work date will also follow the calendar day.  

## Example  
 This example shows how to use the WORKDATE method. 
 
```  
var
    NewDate: Date;
    Text000: Label 'The new work date is: %1';
begin
    NewDate := WORKDATE(20180101D);  
    MESSAGE(Text000, NewDate);  
end;
```  

The code sets the work date to January 1, 2018, and returns the new date in a message. On a computer that has the regional format set to English \(United States\), the message window displays the following:  

 **The work date is: 01/01/18**  

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
---
title: "NormalDate Method"
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
# NormalDate Method
Gets the regular date (instead of the closing date) for the argument Date.


## Syntax
```
NormalDate :=   System.NormalDate(Date: Date)
```
> [!NOTE]  
> This method can be invoked without specifying the data type name.  
## Parameters
*Date*  
&emsp;Type: [Date](../date/date-data-type.md)  
The input date. You can enter a closing date or a normal date. A run-time error occurs if the value of Date is set to the undefined date (0D).  


## Return Value
*NormalDate*  
&emsp;Type: [Date](../date/date-data-type.md)  
  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Example  
 The input date is a regular date.
  
```
var
    InputDate: Date;
    OutputDate: Date;
    Text000: Label 'The normal date for %1 is %2.';
begin
    InputDate := 20140404D;  
    OutputDate := NORMALDATE(InputDate);  
    MESSAGE(Text000, InputDate, OutputDate);  
end;
```  
  
 On a computer that has the regional format set to English \(United States\), the message window displays the following:  
  
 **The normal date for 04/04/14 is 04/04/14.**  
  
## Example  
 The input date is a closing date.
  
```  
var
    InputDate: Date;
    OutputDate: Date;
    Text000: Label 'The normal date for %1 is %2.';
begin
    InputDate := CLOSINGDATE(20140404C);  
    OutputDate := NORMALDATE(InputDate);  
    MESSAGE(Text001, InputDate, OutputDate);  
end;
```  
  
 On a computer that has the regional format set to English \(United States\), the message window displays the following:  
  
 **The normal date for C04/04/14 is 04/04/14.**  

## See Also
[System Data Type](system-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
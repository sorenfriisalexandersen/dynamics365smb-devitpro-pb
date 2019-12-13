---
title: "SaveAsPdf Method"
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
# SaveAsPdf Method
Saves a report as a .pdf file.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
[Ok := ]  Report.SaveAsPdf(FileName: String)
```
## Parameters
*Report*  
&emsp;Type: [Report](report-data-type.md)  
An instance of the [Report](report-data-type.md) data type.  

*FileName*  
&emsp;Type: [String](../string/string-data-type.md)  
The path and name of the file that you want to save the report as.
          


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 You can use the **SAVEASPDF** method on the global REPORT object or on Report variables. If, at design time, you do not know the specific report that you want to run, then use the global REPORT object and specify the report number in the *Number* parameter. If you do know which report you want to run, then create a Report variable, set the Subtype of the variable to a specific report, and use this variable when you call the **SAVEASPDF** method.  

 When you call **SAVEASPDF**, the report is generated and saved to "*FileName*." A **Saving to PDF** window shows the status of the process. Note that the request page will not be shown.  

 The *FileName* parameter specifies a location on the computer that is running [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)]. If you call this method from a client, such as from an action on a page, then use the [DOWNLOAD Method \(File\)](../../methods/devenv-download-method-file.md) to download the .pdf file from the computer that is running [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)] to the computer that is running the client.  

> [!NOTE]  
>  By default, when a report uses an RDLC report layout at runtime, fonts are embedded in the generated PDF. You can specify whether fonts are embedded in the PDF for RDLC reports by changing the **Report PDF Font Embedding** setting in the [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)] instance configuration or changing the **PDFFontEmbedding** property in report objects. <!--NAV For more information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md) and [PDFFontEmbedding Property](../properties/devenv-PDF-FontEmbedding-Property.md).-->  

## Example  
 This example shows how to use the **SAVEASPDF** method to save a specific report as a PDF file on the computer that is running [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)]. 
 
```  
var
    Filename: Text;
    ReturnValue: Boolean;
    Report206: Report "Sales - Invoice';
begin
    Filename := 'C:\MyReports\report206.pdf';   
    ReturnValue := Report206.SAVEASPDF(Filename);  
end;
```  


## See Also
[Report Data Type](report-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
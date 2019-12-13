---
title: "WordXmlPart Method"
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
# WordXmlPart Method
Returns the report data structure as structured XML that is compatible with Microsoft Word custom XML parts. The method has an instance call and a static call. The following code shows the syntax of the WORDXMLPART function. The first line of code is the syntax for an instance method call. The second line of code is the syntax for a static method call.


## Syntax
```
String :=   Report.WordXmlPart(Number: Integer [, ExtendedFormat: Boolean])
```
## Parameters
*Number*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The ID of the report that you want to run. If the report you specify does not exist, then a run-time error occurs.
        
*ExtendedFormat*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
If you set this variable to true, then XML elements will include the following attributes attributes:
-   ElementType="Parameter|Column|DataItem". Specifies the element type as defined for the report in Report Designer. Parameter is typically used for elements, such as captions.
-   ElementId="ID". Specifies the ID that is assigned to the element by its ID Property.
-   DataType="Type". Specifies the data type of the element.
If you omit this parameter or set it to false, then the element attributes are not included in the XML. This is the recommended setting when you will use the Word XML part in Word for modifying the report layout because the XML is simpler.
The following example illustrates an XML element that has the ExtendedFormat set to false: <CompanyName ElementType="Column" ElementId="3" DataType="OemText">
The following example illustrates the same XML with the ExtendedFormat set to true:<CompanyName>
          


## Return Value
*String*  
&emsp;Type: [String](../string/string-data-type.md)  
The report data structure as structured XML that is compatible with Microsoft Word custom XML parts.  


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 This method returns the data structure of the report as structured XML that complies with custom XML parts in Microsoft Word 2013. The following table provides a simplified overview of the XML that is returned by the method.  

|XML|Description|  
|---------|-----------------|  
|`<?xml version="1.0" encoding="utf-16"?>`|Header|  
|`<NavWordReportXmlPart xmlns="urn:microsoft-../report/<reportname>/<id>/"`|XML namespace specification. `<reportname>` is the name assigned to the report object. `<id>` is the ID that is assigned to the report.|  
|`..<Labels>`<br /><br /> `....<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<br /><br /> `....<LabelName>LabelCaption</LabelName>`<br /><br /> `..</Labels>`|Contains all the labels for the report. Labels are listed in alphabetical. The element includes labels that are related to columns that have the [IncludeCaption Property](../../properties/devenv-includecaption-property.md) set to **Yes** and labels that are defined in Report Label Designer.<br /><br /> -   Label elements that are related to columns have the format `<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`, where `ColumnName` is determined by the column's [Name Property](../../properties/devenv-name-property.md).<br />-   Label elements from Report Label Designer have the format `<LabelName>LabelCaption</LableName`, where `LabelName` is determined by the label's [Name Property](../../properties/devenv-name-property.md) and `LabelCaption` is determined by the label's [Caption Property](../../properties/devenv-caption-property.md).|  
|`..<DataItem1>`<br /><br /> `....<DataItem1Column1>DataItem1Column1</DataItem1Column1>`|Top-level data item and columns. Columns are listed in alphabetical order.<br /><br /> The element names and values are determined by the Name property of the data item or column.|  
|`....<DataItem2>`<br /><br /> `......<DataItem2Column1>DataItem2Column1</DataItem2Column1>`<br /><br /> `....</DataItem2>`<br /><br /> `....<DataItem3>`<br /><br /> `......<DataItem3Column1>DataItem3Column1</DataItem3Column1>`<br /><br /> `....</DataItem3>`|Data items and columns that are nested in the top-level data item. Columns are listed in alphabetical order under the respective data item.|  
|`..</DataItem1>`<br /><br /> `</NavWordReportXmlPart>`|Closing elements.|  

 Word custom XML parts enable you to integrate business data into Word documents. For example, the WORDXMLPART method is used internally by [!INCLUDE[d365fin_md](../../includes/d365fin_md.md)] when you are creating report layouts in Word. You can use this method to create a custom XML part, and then, together with the [SAVEASXML Method \(Report\)](../../methods-auto/report/report-saveasxml-method.md) method and additional data merging tools, you can implement your own functionality for mapping and laying out report data in Word documents. To create a custom XML part, you can save the return value to an .xml file that is encoded in UTF-16 \(16-bit Unicode Transformation Format\). The resultant file can be added to Word documents as a custom XML part to map the report data set as XML data.  

## Example  
 The following example uses the WORDXMLPART method to save the data structure of Report 112 Sales Statistics in an XML file in a predefined folder *C:\\Report Documents*. The resultant file can be used in Word as a custom XML part. 
 
``` 
var
    ReportAsString Text;
    SalesStatsReport: File;
begin 
    ReportAsString := REPORT.WORDXMLPART(112);  
    SalesStatsReport.TEXTMODE(TRUE);  
    SalesStatsReport.WRITEMODE(TRUE);  
    SalesStatsReport.CREATE('C:\Report Documents\SalesStatsReport.xml', TextEncoding::UTF16);  
    SalesStatsReport.WRITE(ReportAsString);  
    SalesStatsReport.CLOSE;  
end;
```  

 The code generates the report structure as XML, and then writes the XML to the file *C:\\Report Documents\\SalesStatsReport.xml*.  


## See Also
[Report Data Type](report-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
---
title: "SaveAsXml Method"
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
# SaveAsXml Method
Saves the resulting data set of a query as an .xml file.

> [!NOTE]
> This method is supported only in Business Central on-premises.

## Syntax
```
[Ok := ]  Query.SaveAsXml(Number: Integer, FileName: String)
```
## Parameters
*Number*  
&emsp;Type: [Integer](../integer/integer-data-type.md)  
The ID of the query object that you want to save as an .xml file. If the query that you specify does not exist, then a run-time error occurs.
        
*FileName*  
&emsp;Type: [String](../string/string-data-type.md)  
The path and name of the file that you want to save the query to.  


## Return Value
*Ok*  
&emsp;Type: [Boolean](../boolean/boolean-data-type.md)  
**true** if the operation was successful; otherwise **false**.  If you omit this optional return value and the operation does not execute successfully, a runtime error will occur.    


[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 When the **SAVEASXML** method is called, the dataset is generated and then saved in XML format in the file and location that is designated by the *FileName* parameter.  

 The **SAVEASXML** method can be called at any place in the code and does not require that the **CLOSE**, **OPEN**, or **READ** methods are called before it. When the **SAVEASXML** method is called, a new instance of the query is created. The query is implicitly opened, read, and closed. If there is currently a dataset in the opened state when the **SAVEASXML** method is called, then that instance is closed. This means that the following code is unauthorized because the query is not open on the second **READ** call.  

```  
Query.OPEN;  
Query.READ;  
Query.SAVEASXML('c:\test.xml');  
Query.READ;   
```  

 The correct code for this example is as follows.  

```  
Query.OPEN;  
Query.READ;  
Query.SAVEASXML('c:\test.xml');  
Query.OPEN;  
Query.READ;   
```  

## Example  
 The following example shows how to save a query with the name **My Customer Query** as an .xml file. The file is given the name **myquery.xml** and is saved on the c: drive of the computer running [!INCLUDE[d365fin_server_md](../../includes/d365fin_server_md.md)].  

```
var
    MyCustomerQuery: Query "My Customer Query";
    OK: Boolean;
    Text000: Label 'Query was not saved.';
begin
    OK := MyCustomerQuery.SAVEASXML('c:\myquery.xml');  
    if not OK then  
      ERROR(Text000);  
end;
```  

 If the file cannot be saved, then the follow message appears:  

 **Query not saved.**

## See Also
[Query Data Type](query-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
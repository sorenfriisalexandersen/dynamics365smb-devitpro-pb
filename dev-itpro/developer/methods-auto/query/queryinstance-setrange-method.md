---
title: "SetRange Method"
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
# SetRange Method
Sets a filter on a range of values on a column of a query data set.


## Syntax
```
 Query.SetRange(Column: Any [, FromValue: Any] [, ToValue: Any])
```
## Parameters
*Query*  
&emsp;Type: [Query](query-data-type.md)  
An instance of the [Query](query-data-type.md) data type.  

*Column*  
&emsp;Type: [Any](../any/any-data-type.md)  
The name of the column in the query that you want to filter. The name is defined by the column's Name Property.
        
*FromValue*  
&emsp;Type: [Any](../any/any-data-type.md)  
The lower limit of the range. The data type of this parameter must match the data type of Column. If you set only the FromValue parameter, then the ToValue parameter is set to the same value as FromValue.
          
*ToValue*  
&emsp;Type: [Any](../any/any-data-type.md)  
The upper limit of the range. The data type of this parameter must match the data type of Column. If you omit the ToValue parameter, then the only the value that is specified for FromValue is used, which enables you to filter on a single column value instead of a range. If you omit both the FromValue and ToValue parameters, then the method removes all filters that are already set on the column.
          



[//]: # (IMPORTANT: END>DO_NOT_EDIT)

## Remarks  
 SETRANGE is a quick way to set a simple filter on a field. The SETRANGE method is functionally equivalent to calling *Query*.SetFilter\(ColumnName, ‘FromValue..ToValue’\).  
  
 To apply filters to a dataset, the **SETRANGE** method must be called before the **OPEN**, **SAVEASXML**, and **SAVEASCSV** methods, as shown in the following example. To remove filters, you call the [CLEAR Method](../system/system-clear-joker-method.md) or **SETRANGE** without values for the *FromValue* and *ToValue* parameters.  
  
```  
Query.SETRANGE(Column1, FromValue, ToValue);  
Query.OPEN;  
Query.READ;  
CLEAR(Query);  
```  
  
 A call to the **SETRANGE** method automatically closes a query dataset that is currently open. Therefore, the following code is unauthorized and will fail because there is no open dataset for the **READ** method to read.  
  
```  
Query.OPEN;  
Query.READ;  
Query.SETRANGE(Column1, FromValue, ToValue);  
Query.READ;  
```  
  
 In addition to the **SETRANGE** method, you can apply filters to a query using the **SETFILTER** method and the [DataItemTableFilter Property](../../properties/devenv-dataitemtable-filter-property.md) and [ColumnFilter Property](../../properties/devenv-columnfilter-property.md) in Query Designer.  
  
|If the **SETRANGE** method...|then...|  
|-------------------------------------|-------------|  
|Sets a filter on the same field as the **DataItemTableFilter** property|The two filters are joined into a resulting filter.|  
|Sets a filter on the same field as the **ColumnFilter** property|The **SETRANGE** method overwrites the **ColumnFilter** property, so the filter that is set by the **SETRANGE** method that is applied to the dataset.|  
|Sets a filter on the same field as the **SETFILTER** method|The method that is called last is applied to the dataset.|  
|Sets a filter on a field that has global filters that are applied by the **FILTERGROUP\(1\)** method|The filters of the **SETRANGE** method are added to the global filters.|  
  
 For example, a query has the following filters set on the **Quantity** column in Query Designer:  
  
-   **DataItemTableFilter** property: Quantity=FILTER\(\<>10\)  
  
-   **ColumnFilter** property: Quantity=FILTER\(\<>5\)  
  
 `Query.setRange(Quantity, 1, 15)` will result in a filter that is equivalent to: 1 \< Quantity \<15, except for 10.  
  
 <!--Links For more information about how to set filters in Query Designer, see [Understanding Query Filters](Understanding-Query-Filters.md). --> 
  
## Example  
 The following AL code example demonstrates how to use the **SETRANGE** method on a query. The example code sets a filter on a query column and saves the resulting dataset as a CSV file. A message also displays when the query is run that indicates the filter on the column.  
  
 This example requires that you do the following:  
  
1.  Create a query called **Customer\_SalesQuantity** that has the following characteristics:  
  
    -   Links table **18 Customer** with table **37 Sales Lines** from the [!INCLUDE[demolong](../../includes/demolong_md.md)].  
  
    -   Includes columns for the **Name** and **No.** fields from the Customer table and the **Quantity** field from Sales Lines table.  

  
2.  Create the following AL variables and text constant in the object that will run the query, such as a codeunit.  
  
      ```
     var
        MyQuery: Query "Customer SalesQuantity";
        Text000: Label 'Customer name = %1, Quantity = %2';
    ``` 
  
 The following AL code uses the **SETRANGE** method to filter a query dataset over a range of values on the **Quantity** column. You can add the code to a codeunit, and then run the codeunit to see the results.  
  
```  
// Sets a filter to display only sales quantities greater than 10.  
MyQuery.SETRANGE(Quantity, '10', '50');  
// Sets a filter to display the columns with the value Selangorian Ltd. only.  
MyQuery.SETFILTER(NAME, 'Selangorian Ltd.');  
// Runs the query.  
MyQuery.OPEN;  
// Reads each row in the dataset and displays message with column values.  
// Stops reading when there are no more rows remaining in the dataset (READ is FALSE).  
while MyQuery.READ do  
begin  
  MESSAGE(Text000, MyQuery.Name, MyQuery.Quantity);  
end;   
// Saves the resulting dataset as a CSV file.  
MyQuery.SAVEASCSV('c:\temp\CustomerSales.csv');  
MyQuery.CLOSE;  
```  
  
 When the code is run, a message that resembles the following appears for each row in the dataset:  
  
 **Customer name = Selangorian Ltd., Quantity = 30**

## See Also
[Query Data Type](query-data-type.md)  
[Getting Started with AL](../../devenv-get-started.md)  
[Developing Extensions](../../devenv-dev-overview.md)
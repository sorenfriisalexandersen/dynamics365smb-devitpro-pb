---
title: "API Query Type"
description: "Description of the API query type used for exposing and viewing web service endpoints."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/01/2019
ms.topic: article
ms.author: solsen
---

# API Query Type
Queries of the type `API` are used to generate web service endpoints and this type of page cannot be displayed in the user interface. A query of the API type can be used to join data from different data sources. The data can only be viewed. When creating this query type, you must specify a number of properties that provide information for the web service endpoint. Use the snippet `tquery - Query of type API` to get the right template and the list of these properties automatically filled in.

## Example of the API query type
The following query example publishes an API available at:
`../contoso/app1/v1.0/companies({id})/customerSales`. The `APIVersion` can be specified as one version, or a list of versions, if the API is supported through multiple versions.

```
query 20000 "APIV1 - Customer Sales"
{
    QueryType = API;
    APIPublisher = 'contoso';
    APIGroup = 'app1';
    APIVersion = 'v1.0';
    Caption = 'customerSales', Locked = true;
    EntityName = 'customerSale';
    EntitySetName = 'customerSales';

    elements
    {
        dataitem(QueryElement1; Customer)
        {
            column(customerId; Id)
            {
                Caption = 'Id', Locked = true;
            }
            column(customerNumber; "No.")
            {
                Caption = 'No', Locked = true;
            }
            column(name; Name)
            {
                Caption = 'Name', Locked = true;
            }
            dataitem(QueryElement10; "Cust. Ledger Entry")
            {
                DataItemLink = "Customer No." = QueryElement1."No.";
                SqlJoinType = LeftOuterJoin;
                DataItemTableFilter = "Document Type" = FILTER (Invoice | "Credit Memo");
                column(totalSalesAmount; "Sales (LCY)")
                {
                    Caption = 'TotalSalesAmount', Locked = true;
                    Method = Sum;
                }
                filter(dateFilter; "Posting Date")
                {
                    Caption = 'DateFilter', Locked = true;
                }
            }
        }
    }
}
```

## See Also
[AL Development Environment](devenv-reference-overview.md)  
[API Page Type](devenv-api-pagetype.md)  
[Query Object](devenv-query-object.md)  
[Developing Extensions](devenv-dev-overview.md)  

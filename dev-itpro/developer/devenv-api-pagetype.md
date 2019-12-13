---
title: "API Page Type"
description: "Description of the API page type used for exposing web service endpoints."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/01/2019
ms.topic: article
ms.author: solsen
---

# API Page Type

Pages of the type `API` are used to create versioned, webhook-supported, OData v4 enabled REST web services. This type of page cannot be displayed in the user interface, but is intended for building reliable integration services. When creating this page type, you must specify a number of properties that provide information for the web service endpoint. Use the snippet `tpage - Page of type API` to get the right template and the list of these properties automatically filled in. This page type cannot be extended by creating a page extension object. Instead, you must create a new API by adding a page object.

## Naming conventions

For the API page type, the following naming conventions exist:

- camelCase for naming attributes, tables, as well as APIPublisher, APIGroup, EntityName, and EntitySetName.
- Alphanumeric characters allowed (A-Z+a-z+0-9) in above elements. 
- APIVersion follows the pattern vX.Y or beta.

At design time, the compiler will show warnings on casing violations and errors on naming violations. Once an API page is deployed, the corresponding [$metadata](/dynamics365/business-central/dev-itpro/developer/devenv-connect-apps-tips) is exposed on the endpoint of the page. 

## Example of the API page type
The following page example publishes an API available at:
`../contoso/app1/v2.0/companies({id})/customers`. The `APIVersion` can be specified as one version, or a list of versions, if the API is supported through multiple versions.

```
page 50120 MyCustomerApi
{
    PageType = API;
    Caption = 'My Customer API';
    APIPublisher = 'contoso';
    APIGroup = 'app1';
    APIVersion = 'v2.0';
    EntityName = 'customer';
    EntitySetName = 'customers';
    SourceTable = Customer;
    DelayedInsert = true;
    
    layout
    {
        area(Content)
        {
            repeater(GroupName)
            {
                field(id; Id)
                {
                    Caption = 'ID';
                }
                field(name; Name)
                {
                    Caption = 'Name';
                }
            }
        }
    }
}
```

## See Also  
[AL Development Environment](devenv-reference-overview.md)  
[API Query Type](devenv-api-querytype.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Developing Extensions](devenv-dev-overview.md)  

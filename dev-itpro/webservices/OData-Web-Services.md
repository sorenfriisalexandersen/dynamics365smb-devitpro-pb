---
title: "OData Web Services"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
---

# OData Web Services

The Open Data Protocol \(OData\) is a web protocol that is designed for querying tabular data and provides you with an alternative to SOAP-based web services. OData builds on web technologies such as HTTP, the Atom Publishing Protocol \(AtomPub\), and JavaScript Object Notation \(JSON\) to provide access to information from different applications, services, and stores. OData uses URIs for resource identification and commits to an HTTP-based, uniform interface for interacting with resources. This commitment to core Web principles allows for OData to enable a new level of data integration and interoperability across a broad range of clients, servers, services, and tools.  
  
 You can use OData web services to show [!INCLUDE[prodshort](../developer/includes/prodshort.md)] data, and you can update data in a [!INCLUDE[prodshort](../developer/includes/prodshort.md)] database using OData web services.  
  
 OData can be found in other Microsoft products and technologies, including the following:  
  
-   Microsoft Excel implements OData for its PowerPivot add-in.  
  
-   Microsoft SharePoint can expose its list-oriented data with OData.  
  
-   Microsoft Azure Table Services are based on OData.  
  
 The topics in this section describe the key concepts and techniques for accessing [!INCLUDE[prodshort](../developer/includes/prodshort.md)] data from OData applications that are supported by [!INCLUDE[prodshort](../developer/includes/prodshort.md)] .  
  
|To|See|  
|--------|---------|  
|Use OData to obtain an AtomPub document.|[Using OData to Return or Obtain an AtomPub Document](Return-Obtain-an-AtomPub-Document.md)|  
|Use OData to obtain a service metadata \(EDMX\) document.|[Using OData to Return or Obtain a Service Metadata \(EDMX\) Document](return-obtain-service-metadata-edmx-document.md)|  
|Use OData to obtain a JavaScript Object Notation \(JSON\) document.|[Using OData to Return-Obtain a JSON Document](return-obtain-json-document.md)|  
|Use filter expressions in OData URIs.|[Using Filter Expressions in OData URIs](Use-Filter-Expressions-in-OData-URIs.md)|  
|Use FlowFilters in OData URIs.|[Using FlowFilters in OData URIs](use-flowfilters-in-odata-uris.md)|  
|Use server-driven paging in OData URIs.|[Server-Driven Paging in OData Web Services](Server-Driven-Paging-in-OData-Web-Services.md)|  
|Navigate in an OData web service application by using resource properties.|[Using Containments and Associations](use-containments-associations.md)|  
|Write to the database through an OData web service that exposes a writable page.|[Using OData Web Services to Modify Data](use-odata-to-modify-data.md)|  

## Enabling and Configuring OData on the [!INCLUDE[server](../developer/includes/server.md)]
 
The [!INCLUDE[server](../developer/includes/server.md)] instance has several configurations settings that enable and control OData services. For more information, see [OData Services Settings](../administration/configure-server-instance.md#ODataServices).

## Known Limitations
 
You can specify filters in OData web services in general that are not supported in [!INCLUDE[prodshort](../developer/includes/prodshort.md)] , such as using an OR operator to filter on two different fields. In those cases, you will see the following error:  
  
```  
An error occurred while processing this request.   
 The 'OR' operator is not supported on distinct fields on an OData filter.  
```  
  
## See Also  
 [SOAP Web Services](SOAP-Web-Services.md)

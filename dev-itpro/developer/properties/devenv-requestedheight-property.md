---
title: "RequestedHeight Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: dd671414-a7c3-44bd-a860-a8bda61c7913
caps.latest.revision: 15
author: SusanneWindfeldPedersen
---

 

# RequestedHeight Property

Specifies the ideal height in pixels of the control add-in.

## Applies to 

- Control add-in objects
  
## Value Type 
  
-   Integer 

## Property Values
The default value is 100 pixels.

## Remarks 
This setting is optional. You can use it when the visual content of the add-in is optimal at a specific size. If space is available on the page, the requested height will be applied. If the add-in must compete for space with other content on the page, such as a second add-in, then the RequestedHeight value is ignored and the add-in will shrink or stretch to the minimum or maximum height.
The value of RequestedHeight is ignored if the add-in is the only content on a card page.

## Code Example
```
RequestedHeight = 300;
VerticalShrink = true;
MinimumHeight = 150;

```

## See Also  
[Control Add-In Object](../devenv-control-addin-object.md)   
 
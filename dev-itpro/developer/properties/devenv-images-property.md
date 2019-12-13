---
title: "Images Property"
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

 

# Images Property

Specifies the list of images to include in the control add-in. The property is optional. 

## Applies to 
- Control add-in objects 

## Property Values 
A list of comma-separated strings that represents paths to image files. The default is blank, with no images being used by the control add-in. 

## Remarks
The Images property specifies image resources that are referenced by the control add-in scripts. Any specified images must be of a supported web format and extension, such as .PNG or .GIF. 

Images can be either external resources referenced using a URL or can be embedded within the extension. Embedded images must be added to the extension project folder in Visual Studio Code and referenced using a relative path. At runtime, the path to an embedded can be obtained using the [GETIMAGERESOURCE](../methods/devenv-getimageresource-method.md) method. Unlike scripts and stylesheets, images are loaded on demand when they are first used in code. Since images are stored in the application after the extension is deployed, it is recommended to keep the number of image files and combined image size to a minimum. 

## Code Example
```
Images = 'https://fabrikam.com/banner.png',
              'images/map.png';
```
  


## See Also  
[Control Add-In Object](../devenv-control-addin-object.md)   
 
---
title: "AutoFormatExpression Property"
ms.author: solsen
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
ms.assetid: 18e6df94-639e-4c5f-99ed-5729037bb719
caps.latest.revision: 13
author: SusanneWindfeldPedersen
---

# AutoFormatExpression Property
Sets an AL expression that specifies how to format data.  
  
## Applies To  
 Fields (or columns) of the decimal data type in the following objects:  
  
-   Tables  
  
-   Pages  
  
-   Reports  
  
## Syntax
```
AutoFormatExpression = '<Currency Code>';
AutoFormatType = 2;
```


## Remarks

The AL expression is evaluated when the expression performs updates. Together with the [AutoFormatType Property](devenv-autoformattype-property.md), this property determines how data is formatted. These two properties are only used to format decimal data types, such as amounts that can be stated in a foreign currencies or ratios.

For more information, see [Formatting Decimal Values in Fields](../devenv-format-field-data.md).

## Example

The following example uses **AutoFormatExpression** property to set the format of decimal values to USD.

```
AutoFormatExpression = 'USD';
AutoFormatType = 1;
```

For example, this will result in a value like 7,564.00.


Changing the **AutoFormatExpression** property to `ÌRD` sets the format of decimal values to IDR \(Indonesian rupiah\).

```
AutoFormatExpression = 'IRD';
AutoFormatType = 1;
```
For example, this will result in a value like 7,564.

## Example

The following example is similar to the previous example, except it adds a $ sign before the amount.

```
AutoFormatExpression = '1,USD';
AutoFormatType = 10;
```

For example, this will result in a value like $7,564.00.

## Example

This example prefixes the decimal value with a $, includes a thousand separator, and has a maximum of two decimal places, such as $76,453.21:

```
AutoFormatType = 1;
AutoFormatExpression = '$<precision, 2:2><standard format, 0>
```
## See Also

[AutoFormatType Property](devenv-autoformattype-property.md)  
[DecimalPlaces Property](devenv-decimalplaces-property.md)
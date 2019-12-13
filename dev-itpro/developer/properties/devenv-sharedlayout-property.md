---
title: "SharedLayout Property"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
author: SusanneWindfeldPedersen
---

# SharedLayout Property
The `SharedLayout` property specifies whether a view has the same layout as the default view **All**.

## Applies To  
- Views

## Property Values  
When set to **true**, user personalization on the page is also applied when the view is selected. When set to **false**, the view defines its own layout and is not affected by user personalization.


## Syntax
```
SharedLayout = false;
``` 
  
## Remarks  

### Shared layout view
A view with `SharedLayout = true` follows the design of the **All** page and any user personalization made on **All** or any of the views marked with `SharedLayout` are applied on the view. They all share the same layout. This is a basic experience in the case where defining a specific layout for the view is not important. The view is then filter only. 

#### Example

```
view(SharedLayoutView) 

{ 
    // This view only define filters, but no specific layout. 
    // User personalization are applied on this view. 
    Caption = 'View With Shared Layout'; 
    Filters = where("Balance Due (LCY)" = filter(> 10000)); 
} 
```

### Detached layout view
A view with detached layout `SharedLayout = false` defines its own layout and is independent from all other views. Any changes coded in the layout sections are applied in the view. User personalization made on the page are not applied on that view.

### Example

```
view(DetachedView)
{
	Caption = 'View With Detached Layout';
	Filters = where("Balance Due (LCY)" = filter(> 10000));
	// By settings this property to false, the view gets its own independent layout.
	// User personalization are not applied on this view.
	// Instead, the layout defined below is applied.
	SharedLayout = false;
	
	layout
	{
		movefirst(Control1; "Balance Due (LCY)")
	}
}
```

> [!NOTE]  
> `SharedLayout = false` must be specified in order to use a custom layout on the view (the layout section). A compiler error is reported otherwise.


## See Also
[Properties](devenv-properties.md)  
[Views](../devenv-views.md)
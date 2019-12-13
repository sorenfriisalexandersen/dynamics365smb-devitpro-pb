---
title: "How to: Mount or Dismount a Tenant on a Dynamics 365 Business Central Server Instance"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
---
# Mount or Dismount a Tenant on a Microsoft Dynamics Server Instance
If a [!INCLUDE[server](../developer/includes/server.md)] instance is configured for multitenancy, then you can mount and dismount tenant databases by using the [!INCLUDE[admintool](../developer/includes/admintool.md)] or **Mount-NAVTenant** or **Dismount-NAVTenant** cmdlets in [!INCLUDE[adminshell](../developer/includes/adminshell.md)].  

 Mounting a tenant by using the [!INCLUDE[admintool](../developer/includes/admintool.md)] requires that you have a running [!INCLUDE[server](../developer/includes/server.md)] instance. This is not required when you use the [!INCLUDE[adminshell](../developer/includes/adminshell.md)]. With the **Mount-NAVTenant**, you can mount a tenant by either specifying the [!INCLUDE[server](../developer/includes/server.md)] instance, if it is running, or the application database.  

 This topic describes how to use the [!INCLUDE[admintool](../developer/includes/admintool.md)] to mount or dismount a tenant. For more information about how to use the [!INCLUDE[adminshell](../developer/includes/adminshell.md)], see [Mount-NAVTenant](https://go.microsoft.com/FwLink/?LinkId=401372) and [Dismount-NAVTenant](https://go.microsoft.com/FwLink/?LinkId=401354).  

### To mount or dismount a tenant  

1.  Open the [!INCLUDE[admintool](../developer/includes/admintool.md)].  

2.  Verify that the [!INCLUDE[server](../developer/includes/server.md)] that you want to mount the tenant on is running, and if not, then start it:  

    1.  In the left pane of [!INCLUDE[admintool](../developer/includes/admintool.md)], choose a [!INCLUDE[server](../developer/includes/server.md)] computer. Unless you are administering a remote computer, this is **[!INCLUDE[prodlong](../developer/includes/prodlong.md)] \(local\)**.  

    2.  In the center pane, if the **Status** of the [!INCLUDE[server](../developer/includes/server.md)] instance is **Stopped**, then right-click it, and then choose **Start**.  

3.  In the left pane, expand item for the [!INCLUDE[server](../developer/includes/server.md)] instance on which you want to mount the tenant, and then choose the **Tenants** item.  

4.  To mount a tenant, in the **Actions** pane, choose **Mount Tenant**, fill in the parameters on the **Mount Tenant** dialog box, and then choose the **OK** button.  

     To get help on a setting, place your point on caption to display a tooltip.  

    
5.  To save the changes, choose the **OK** button.  

     If you specified the **DatabaseUserName** and **ProtectedDatabasePassword** settings for SQL Server authentication, on the **Enable Encryption on SQL Server Connections** dialog box, choose the **OK** button.  

     Encryption keys are to secure the login credentials over the connection between the [!INCLUDE[server](../developer/includes/server.md)] instance and the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] database in SQL Server.  

6.  Choose the **OK** button to save the changes.  

### To dismount a tenant  

-   In the center pane, right-click the tenant, and then choose **Dismount Tenant**.  

## See Also  
 [Server Administration Tool](administration-tool.md)   
 [Multitenant Deployment Architecture](../deployment/Multitenant-Deployment-Architecture.md)

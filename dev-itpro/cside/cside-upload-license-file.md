---
title: "How to: Upload the License File"
ms.custom: na
ms.date: 10/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: "dynamics365-business-central"
---
# Uploading the License File
After an administrator or a Microsoft Certified Partner initially installs [!INCLUDE[prodshort](../developer/includes/prodshort.md)], the next step is to upload the license file that is supplied by Microsoft.  

 To save the license file, you must have the Per Database license granule \(2020\) in your license. You must also have the necessary roles and permissions in SQL Server. See [Setting Database Owner and Security Administration Permissions](../security/Setting-Database-Owner-and-Security-Administration-Permissions.md).  

> [!NOTE]  
>  Uploading the license file is typically something you do once for each database installation, not once for each client installation. If you need to upload a license for a specific database, see [Uploading a License File for a Specific Database](#UploadtoDatabase).  

 Initially, [!INCLUDE[prodshort](../developer/includes/prodshort.md)] uses CRONUS.flf, which is the demonstration license file. All license files that are not demonstration license files are named FIN.flf. The demonstration license file has been given a different name so that it cannot be mistakenly overwritten.  

## Upload the License File to SQL Server  
 The following procedure uploads the license for all [!INCLUDE[prodshort](../developer/includes/prodshort.md)] databases on the SQL Server instance.  

1.  Start the [!INCLUDE[nav_dev_long](../developer/includes/nav_dev_long_md.md)].  

    > [!NOTE]  
    >  On a computer running any version of Windows with User Access Control enabled, you must start the development environment as an administrator.  

2.  Verify that you are connected to your database. On the **File** menu, point to **Database**, and then choose **Open**.  

3.  Upload the new license.  

    1.  On the **Tools** menu, choose **License Information**.  

    2.  In the **License Information** window, choose **Upload**.  

    3.  In the **Upload License File** dialog box, browse to and open the license file.  

     You should see the following message:  

     **The Server license was successfully uploaded.**  

4.  Restart the [!INCLUDE[nav_dev_short](../developer/includes/nav_dev_short_md.md)] to activate the license.  

5.  Restart all [!INCLUDE[server](../developer/includes/server.md)] instances on the computer to activate the license for other clients.  

> [!NOTE]  
>  Always review your license file after uploading, to verify that all information is correct and that you have all necessary license granules.  

##  <a name="UploadtoDatabase"></a> Uploading a License File for a Specific Database  

1.  In the development environment, on the **File** menu, point to **Database**, and then choose **Alter**.  

2.  In the **Alter Database** window, choose **Integration**, and then select **Save license in database**.  

3.  Restart all [!INCLUDE[server](../developer/includes/server.md)] instances on the computer to activate the license for other clients.  

## See Also  
 [Microsoft Dynamics ERP Software License Terms (requires login)](https://go.microsoft.com/fwlink/?LinkId=247426)   
 [Microsoft Dynamics ERP Licensing Guide (requires PartnerSource login)](https://go.microsoft.com/fwlink/?LinkID=318024)

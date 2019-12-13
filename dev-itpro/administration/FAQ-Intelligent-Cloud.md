---
title: Frequently Asked Questions | Microsoft Docs
description: Get answers to your questions about connecting to the intelligent cloud from an on-premises solution through Business Central.
author: bmeier94

ms.reviewer: edupont
ms.service: dynamics365-business-central
ms.topic: article
ms. search.keywords: cloud, edge
ms.date: 10/01/2019
ms.author: bmeier

---

# Frequently Asked Questions about Connecting to the Intelligent Cloud from On-Premises Solutions

This section contains answers to frequently asked questions about connecting on-premises solutions to the intelligent cloud through [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online.  

## Which products and versions are supported for this connection?

The current version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)] can connect the following products in order to provide intelligent insights:

- Dynamics GP 2018 R2
- [!INCLUDE[prodshort](../developer/includes/prodshort.md)] on-premises
- Dynamics NAV 2018 CU 16

    Support added with the April 2019 [!INCLUDE[prodshort](../developer/includes/prodshort.md)] update. However, the 2019 release wave 2 removes support for migrating from Dynamics NAV 2018 to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online. Instead, you must upgrade to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] on-premises, and then switch to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online. For more information, see [Migrations to Business Central online](/dynamics365-release-plan/2019wave2/dynamics365-business-central/migrations-cloud) in the 2019 release wave 2 release plan.<!--
        **NAV2018 will only be supported up to the Wave2 Release of Business Central.  This update will release approximately the beginning of Octover 2019. With the Wave2 release a customer will need to update their on premise if they want to migrate to the cloud.  **See the Wave 2 release notes for more information.-->
<!-- - Dynamics SL 2018 CU 1-->

## How is my on-premises data replicated to my [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant?

Data is replicated using an Azure service called Azure Data Factory (ADF). The Azure Data Factory is a service that is always running within the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online service manager. When the intelligent cloud is configured for your on-premises solution, a data pipeline is created within the ADF service that enables data to flow from your on-premises solution to your Business Central cloud tenant. If your data source is a local SQL Server instance, you will also be asked to configure a self-hosted integration runtime (SHIR). The runtime is installed locally and enables the communication between the cloud services and your on-premise data to communicate without opening any ports or firewalls.  

## Are there any limits on the amount or type of data will replicate?

Data replication for the initial release will have a limit of 150GB.  There are no restrictions on the type of data that can be replicated.  

## Is my SQL connection string required to set up the connection?

Yes. The SQL connection string is passed to Azure Data Factory, where it is encrypted and delivered to your Self-Hosted Integration Runtime, and used to communication with your SQL Server instance during the data replication process. For more information, see [How do I find my SQL connection string?](#how-do-i-find-my-sql-connection-string).  

## I am a hosting partner - do I need to configure the Self-Hosted Runtime Service for each tenant?

No, there is no limit on the number of tenants that can be added to your Self-Hosted Integration Runtime. Each added tenant will have a dedicated pipeline created.

## Will data from tables with code customizations replicate?

No, only tables that are available in both your on-premises solution and your [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant will replicate. Any customization would need to be made into an extension and installed on both your on-premises solution and your [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant to replicate.  

## Why are my permissions restricted in the Business Central online tenant?

When you connect your on-premises solution to [!INCLUDE [prodshort](../developer/includes/prodshort.md)] online for intelligent insights, all existing users are automatically added to the *Intelligent Cloud* user group, unless they have the SUPER permission set. In this configuration, your on-premises solution is the master where all business transactions take place. The [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online environment is read-only, and the data is used to generate intelligent business insights based on your on-premises data for you. We restrict permissions to prevent users from accidentally entering transactions or updating master records only to have that information overwritten and lost when data replication takes place.  

## Can I ‘turn off’ my intelligent cloud?

You can switch off your connection to the [!INCLUDE [prodshort](../developer/includes/prodshort.md)] online environment at any point. Once you disable your intelligent cloud configuration, your on-premises solution and the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant will become completely independent of one another. If you switch off the connection, and you want to use your [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online environment as your primary solution to run and manage your business, you must reassign permissions to provide read/write access to the relevant users.  

For more information, see [Managing Users and Permissions](/dynamics365/business-central/ui-how-users-permissions).  

## Will my on-premises users and permissions replicate?

No. Since you are not required to configure your on-premises solution with Azure Active Directory (Azure AD), we cannot guarantee a mapping between on-premises users and users in your [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant. [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online requires Azure AD accounts, and users must be manually added. All permissions must be granted in the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] tenant, independent from your on-premises permissions.  

For more information, see [Managing Users and Permissions](/dynamics365/business-central/ui-how-users-permissions).  

## Can I view insights from cloud services in my on-premises solution?

Yes, the **Intelligent Cloud Insights** page can be hosted within your on-premises solution if that is one of [the currently supported solutions](#which-products-and-versions-are-supported-for-this-connection). Each user will need to have a [!INCLUDE[prodshort](../developer/includes/prodshort.md)] license to view the data.  

## Can you export to Excel, modify the contents, and import the data back in?

You can export the list to Excel from the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant, but since the data is read-only you cannot make changes and import it again.  

## Is the data replication only one-way?

Yes, data is only replicated from the on-premises solution to your Business Central online tenant.  

## Is there a cost to connect to the intelligent cloud?

Currently, the only costs associated with the intelligent cloud are your named user license costs. For more information, see the [Business Central Licensing Guide (download)](https://go.microsoft.com/fwlink/?LinkId=871590).  

## Why did my Role Center change after configuring the intelligent cloud?

To keep the Role Center experience as clean as possible and avoid permission errors, we automatically hide actions that would generate a permission error for the user.  

## Should I uninstall all my Business Central extensions?

Not necessarily. Most extensions will run without issues in the online environment. You may want to consider uninstalling extensions that send data to an external service to avoid potential duplicated calls to that service. It is a best practice to test any extension in a sandbox tenant configured for the Business Central online environment that you are connecting to.  

## How do I build an extension that enables data replication?

The extension must be created in the same manner as any other extension. For data to replicate, you must add a **ReplicateData** property to your table and set the value to *True*. If your extension connects with an external service and you want to restrict any service calls from your [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant, a good practice would be to store the connection information in a separate table and set the **ReplicateData** property to *False*. This would enable you to keep the extension installed but prevent it from making any type of service calls from the read-only [!INCLUDE[prodshort](../developer/includes/prodshort.md)] tenant. Once the extension is installed in [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online and on-premises, the data will begin to replicate.  

## How do I find my SQL connection string?

A connection string to your SQL database can be found in SQL Management Studio or using Visual Studio. The user name and password defined in the connection requires a SQL Authenticated user name/password. Your connection string should look something like this:

*Server=tcp:{ServerName},1433;Initial Catalog={DatabaseName};Persist Security Info=False; User ID={UserName};Password={Password};MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=True;Connection Timeout=30;*

## How do I find the Integration Runtime name?

The Integration Runtime name can be found in the Microsoft Integration Runtime Manager. You can find this application in your Windows system tray or by searching for the program. You will not be able to copy and paste the name. You must manually type the name.  

## Can I connect my Microsoft Invoicing data to the intelligent cloud?

No. Microsoft Invoicing currently does not support connecting to the intelligent cloud through [!INCLUDE[prodshort](../developer/includes/prodshort.md)]. If your organization has an existing Invoicing tenant and want to create a [!INCLUDE[prodshort](../developer/includes/prodshort.md)] tenant, you must contact Support to have them delete your existing Invoicing tenant.  

For more information, see [Using the same Office 365 Account in Dynamics 365 Business Central and Microsoft Invoicing](/dynamics365/business-central/about-reuse-company-invoicing).  

## See also

[Connect to the intelligent cloud with Business Central](about-intelligent-edge.md)  
[Managing your intelligent cloud environment](manage-intelligent-edge.md)  
[Replicating on-premises data](data-replication-intelligent-cloud.md)  
[ReplicateData Property](../developer/properties/devenv-replicatedata-property.md)  

---
title: Upgrade Considerations
description: This article provides tips and considerations to prepare a solution when you are planning to upgrade Microsoft Dynamics 365 Business Central.
author: jswymer
ms.custom: na
ms.reviewer: edupont
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-business-central
ms.date: 10/01/2019
ms.author: jswymer
---
# Important Information and Considerations for Before Upgrading to [!INCLUDE[prodlong](../developer/includes/prodlong.md)] Spring 2019

Depending on which version you are upgrading from, and the degree to which your solution differs from the standard version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)], you may want to prepare your solution for the upgrade. This topic provides important information and tips for things to consider when you prepare to upgrade to [!INCLUDE[prodshort](../developer/includes/prodshort.md)].  

## Upgrading from [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)] to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online

You can upgrade to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online from supported versions of [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)] on-premises, provided that your application customization is handled by extensions. Any data from tables with code customizations cannot be carried forward from [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)].  

> [!IMPORTANT]
> Upgrading from [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)] to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online is only partially supported. In the current version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)], when you connect your on-premises solution to the intelligent cloud, the on-premises deployment remains the primary application, and the cloud tenant is, with very few exceptions, read-only. For more information, see [Connect to the intelligent cloud](../administration/about-intelligent-edge.md).

The process consists of two parts:

- Upgrade from [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)] to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] using the tools described in [Upgrading to Business Central on-premises](upgrading-to-business-central-on-premises.md).
- Convert non-standard functionality and customizations to apps and per-tenant extensions. For more information, see [Deploying a Tenant Customization](../developer/devenv-deploy-tenant-customization.md).
- Enable replication to a cloud tenant as described in [Connect to the intelligent cloud](../administration/about-intelligent-edge.md), and then switch to use the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] online tenant going forward.

## Upgrading from [!INCLUDE[navnow_md](../developer/includes/navnow_md.md)]

### Codeunit 1 has been deprecated and replaced

[!INCLUDE[navnow_md](../developer/includes/navnow_md.md)] included codeunit **1 ApplicationManagement**. In [!INCLUDE[prodshort](../developer/includes/prodshort.md)], this codeunit has been retired, and new ‘system’ codeunits have been introduced in the 2 billion range.

For information, see [Transitioning from Codeunit 1 to System Codeunits](transition-from-codeunit1.md).

### V1 Extensions have been discontinued

With [!INCLUDE[prodshort](../developer/includes/prodshort.md)], extensions V1 are no longer supported for on-premise installations. As a result, any custom extensions V1 must be converted to extensions V2 in the old environment before upgrading to [!INCLUDE[prodshort](../developer/includes/prodshort.md)].

For information about how to convert to extensions V2, see [Converting Extensions V1 to Extensions V2](../developer/devenv-upgrade-v1-to-v2-overview.md).

### MenuSuite not used for page and report search 

With [!INCLUDE[prodshort](../developer/includes/prodshort.md)], the MenuSuite is no longer used to control whether a page or report can be found in the search feature of the Web client. This is now determined by specific properties on the page and report objects. As part of the application code upgrade process, you change these properties on existing pages and reports used by the MenuSuite to ensure that they are still searchable from the Web client. For more information, see [Making Pages and Reports Searchable After an Upgrade](upgrade-pages-report-for-search.md).

## <a name="CRM"></a>[!INCLUDE[crm_md](../developer/includes/crm_md.md)] integration

Because of changes in [!INCLUDE[crm_md](../developer/includes/crm_md.md)] and the  integration since pervious releases, if your application is integrating with [!INCLUDE[crm_md](../developer/includes/crm_md.md)], then you must perform a full upgrade instead of just a technical upgrade.

## New and changed application features

There a several new and changed application features available in [!INCLUDE[prodshort](../developer/includes/prodshort.md)] April 2019 for users, administrators, and developers. For an overview of these features, see [Overview of Dynamics 365 Business Central April '19 release](/business-applications-release-notes/April19/dynamics365-business-central).

To take advantage of these all these features, you will have to perform an application code upgrade, not just a technical (platform) upgrade.  

### Changes to profiles in the [!INCLUDE[demolong_md](../developer/includes/demolong_md.md)] and promoted actions

With the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] April 2019 release, profiles that are part of the [!INCLUDE[demolong_md](../developer/includes/demolong_md.md)], such as the **Sales Order Processor** profile, customize fewer pages compared to earlier releases. For customers that rely on these profiles, their users might experience slight differences in the layout of actions in the action bar on pages. Additionally, the layout of promoted actions on over 380 core application pages has been fine-tuned.

To ensure that users are not disrupted by these changes, we recommend that administrators and partners who are upgrading a customer to [!INCLUDE[prodshort](../developer/includes/prodshort.md)] April 2019, review the layout of promoted actions when combined with their own code and profile customization.

## Names of variables
  
 [!INCLUDE[prodshort](../developer/includes/prodshort.md)] introduces new methods and statements. If your solution includes variables where the name is now used by a standard AL method or statement such as REGISTERTABLECONNECTION or FOREACH, you must change the variables before you upgrade to [!INCLUDE[prodshort](../developer/includes/prodshort.md)]. Alternatively, you can enclose the variable names in quotation marks. If you do not, and you import an object that has this code in text format, you cannot compile the object. 

## Deprecated or redesigned functionality
  
 If you are upgrading a solution that depends on functionality that is deprecated or changed in the default version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)], you must verify that the upgrade codeunits migrate data correctly. See the See Also section for links to descriptions of deprecated functionality.

## Deprecated fields and fields marked as obsolete

Sometimes Microsoft will refactor code so that fields are no longer used, or the functionality is moved from the base application to an extension, for example. Typically, the upgrade toolkit will manage the upgrade impact, but for transparency, you can find a list of fields that are deprecated in the current release or marked to be obsolete in a later release. For more information, see [Deprecated Fields, and Fields Marked as Obsolete](deprecated-fields.md).

## Upgrade codeunits
  
 When you introduce changes to the database schema, [!INCLUDE[prodshort](../developer/includes/prodshort.md)] will check if these changes are destructive or not. If the database check indicates that the change may lead to data deletion, such as if you are dropping a table column so that the contents of that column will be deleted, this is considered a destructive change. You will be prompted to handle the situation using upgrade codeunits. <!-- For more information, see [Upgrade Codeunits]Upgrade-Codeunits.md.-->  

## Company names
  
 If a company name includes a special character, an error may display during the upgrade. In this context, special characters include the following:   
\[ ~ @ \# $ % & \* \( \) . \! % - + / = ? \]  

 If you are going to upgrade a database where one or more company name includes a special character, we recommend that you rename the company before you start the upgrade process. After the upgrade is successfully finished, you can rename the company again.  

## System tables with non-English names
  
 In older versions of [!INCLUDE[navnow](../developer/includes/navnow_md.md)], you could translate the columns in system tables to a language other than English. Starting with version 3.0, we advised heavily against this, and versions later than [!INCLUDE[navsicily](../developer/includes/navsicily_md.md)] require that all columns in all system tables are in English. As a result, if you try to open a database with non-English system tables in [!INCLUDE[navsicily](../developer/includes/navsicily_md.md)] or later, an error displays, saying that one or more columns do not exist.  

 Make sure that all objects where compiled in a development environment with the right .ETX and .STX files. You can verify that you are running in the correct environment with English \(US\) as the base language by opening the **ndo$dbproperty** table in SQL Server Management Studio. In the **Identifiers** column, the word `Object` must be written exactly as shown here.  

## See Also  

[Upgrading the Application Code](Upgrading-the-Application-Code.md)   
[Upgrading the Data](Upgrading-the-Data.md)   
[Deprecated Fields, and Fields Marked as Obsolete](deprecated-fields.md)  

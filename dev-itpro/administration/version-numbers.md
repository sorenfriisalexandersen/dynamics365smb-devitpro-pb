---
title: Version numbers in Business Central
description: Learn what version numbers mean in Business Central to help you troubleshoot any issues.
author: edupont04

ms.topic: article
ms.service: dynamics365-business-central
ms.author: edupont
ms.date: 10/01/2019
---
# Version numbers in Business Central

[!INCLUDE [prodshort](../developer/includes/prodshort.md)] online and on-premises consists of different components that must work together. If you are a an enduser, this doesn't matter in the course of your normal work day. But if you are an administrator, knowing the version numbers is important for troubleshooting, development, and on-premises upgrade scenarios.  

You can use the information about which version the tenant is on to help you troubleshoot an issue that a user has reported, for example. This information is listed in the **Troubleshooting** section of the **Help and Support** page in [!INCLUDE [prodshort](../developer/includes/prodshort.md)] in the following format:

|Version  |Example      |Description                                 |
|---------|-------------|--------------------------------------------|
|Platform \<major>.\<minor>.\<build>.\<revision>|15.0.12345.0 | Specifies the full platform version, which includes client and server components. |
|Application \<major>.\<minor>.\<build>.\<revision>|15.1.23456.0| Specifies the full version number for the application, including the major version number and build number. |

In the [!INCLUDE [prodadmincenter](../developer/includes/prodadmincenter.md)], the version information is rendered slightly differently:

|Version  |Example      |Description                                 |
|---------|-------------|--------------------------------------------|
|Platform  \<major>.\<minor>|15.1 | Specifies the major and minor version of the platform, which includes client and server components. |
|Application \<major>.\<minor>.\<build>.\<revision>|15.1.23456.0 | Specifies the full version number for the application. |

The numbers are updated based on Microsoft's builds. In the default version of [!INCLUDE [prodshort](../developer/includes/prodshort.md)] online, platform and application have the same major version number but different build numbers. If you perform a technical upgrade of [!INCLUDE [prodshort](../developer/includes/prodshort.md)] on-premises, then platform and application will have different versions.  

The following list describes the meaning of each of the numbers in a full version number:

- `major` is the major version of [!INCLUDE[prodshort](../developer/includes/prodshort.md)]

  - `15` is the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] 2019 release wave 2 update in October 2019
  - `14` is the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] April 2019 release
  - `13` is the [!INCLUDE[prodshort](../developer/includes/prodshort.md)] October 2018 release
  - `12` is the April 2018 launch of [!INCLUDE[prodshort](../developer/includes/prodshort.md)]

- `minor` is the monthly update number, such as 1 or 5.
- `build` is the five digit build number, such as 23456.
- `revision` is set to 0 for the original release and can remain at 0. However, if the tenant is patched with a hotfix, then that build number can be applied.

In other words, if you see a version number such as `15.1.23456.26323`, then it means major version *15*, update number *1*, build number *23456*, and hotfix number *26323*.

The same version numbers are used in the on-premises Docker images that you can get for development purposes, and for the on-premises cumulative updates.  

## See Also

[Managing Technical Support](manage-technical-support.md)  
[Installing a Cumulative Update](../upgrade/upgrading-cumulative-update.md)  
[Administration of Business Central Online](tenant-administration.md)  

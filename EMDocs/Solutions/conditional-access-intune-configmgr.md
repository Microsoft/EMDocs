---
# required metadata

title: Use conditional access with Intune and Configuration Manager
description: Deploy the Intune with Configuration Manager solution.
keywords:
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e65a0662-33ff-4e8c-9305-a21e80ea0f69

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer:
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Use conditional access with Intune and Configuration Manager
This topic assumes that you are already using System Center Configuration Manager and Microsoft Exchange Server – with on-premises, Exchange Online, or a hybrid deployment of both – in your company to manage email access. This solution combines your existing Configuration Manager environment with Intune to safely manage email access on all types of devices, regardless of their location.

> [!TIP]
> Get a downloadable copy of this entire topic at the [TechNet Gallery](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

## Before you begin
Before you start using conditional access, ensure that you have the correct requirements in place:

## For Exchange Online
Conditional access to Exchange Online supports devices that run:

-   Windows 8.1 and later (when enrolled with Intune)

-   Windows 7.0 or later (when domain joined)

-   Windows Phone 8.1 and later

-   iOS 7.1 and later

-   Android 4.0 and later, Samsung Knox Standard 4.0 and later

Additionally, devices must be registered with the Azure Active Directory Device Registration Service (AAD DRS).

AAD DRS will be activated automatically for Intune and Office 365 customers. Customers who have already deployed the ADFS Device Registration Service will not see registered devices in their on-premises Active Directory.

-   You must use an Office 365 subscription that includes Exchange Online (such as E3) and users must be licensed for Exchange Online.

-   The optional **Microsoft Intune service to service connector** connects Intune to Microsoft Exchange Online and helps you manage device information through the Intune console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)). You do not need to use the connector to use compliance policies or conditional access policies, but is required to run reports that help evaluate the impact of conditional access.

    If you configure the connector, some Exchange ActiveSync policies from Intune might be visible in the Office console but are not set as default policies and do not affect devices.

    > [!IMPORTANT]
    > Do not configure the service to service connector if you intend to use conditional access for both Exchange Online and Exchange on-premises.

    Now you are ready to learn how to [deploy Exchange Online with Intune](conditional-access-intune-exchange-online.md).

## For Exchange Server on-premises
Conditional access to Exchange on-premises supports:

-   Windows 8 and later (when enrolled with Intune)

-   Windows Phone 8 and later

-   Any iOS device that uses an Exchange ActiveSync (EAS) email client

-   Android 4 and later

Additionally:

-   Your Exchange version must be Exchange 2010 or later. Exchange server Client Access Server (CAS) configuration is supported.

    > [!TIP]
    > If your Exchange environment is in a CAS server configuration, then you must configure the on-premises Exchange connector to point to any one of the CAS servers.

-   Exchange ActiveSync can be configured with certificate based authentication, or user credential entry.

-   You must use the **on-premises Exchange connector** which connects Intune to Microsoft Exchange Server on-premises. This lets you manage devices through the Intune console (see [Mobile device management with Exchange ActiveSync and Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)).

  > [!IMPORTANT]
> Make sure that you are using the latest version of the on-premises Exchange connector. The on-premise Exchange connector available to you in the Intune console is specific to your Intune tenant and cannot be used with any other tenant. You should also ensure that the exchange connector for your tenant is installed on exactly one machine and not on multiple machines.

  Now you are ready to learn how to [deploy Exchange Server on-premises with Intune](conditional-access-intune-exchange.md).

If your environment includes both Exchange Online and on-premises, you can read about [deploying Exchange Online and on-premises with Microsoft Intune and Configuration Manager](conditional-access-intune-configmgr-coexist.md).

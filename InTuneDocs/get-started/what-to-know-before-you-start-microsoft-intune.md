---
title: "Podporovaná zařízení – Microsoft Intune | Dokumentace Microsoftu"
description: "Seznam podporovaných platforem zařízení a prohlížečů pro správu zařízení přes Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 905be6a926dc5bab8e9b1016ba82751ee47313e5
ms.openlocfilehash: 61851f7669e9a5c3a192b2eda344fcde9c4fa3e6
ms.lasthandoff: 03/20/2017


---

# <a name="supported-devices-and-browsers"></a>Podporovaná zařízení a prohlížeče

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Tento článek je určený pro správce systému, kteří se v podniku starají o zařízení. Nápovědu k instalaci Intune do telefonu najdete v článku [Práce pomocí spravovaných zařízení](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions).

Než začnete s nastavováním Microsoft Intune, projděte si následující požadavky:

- [Podporovaná zařízení a počítače](#intune-supported-devices)
- [Seznam podporovaných webových prohlížečů k používání Intune](#intune-supported-web-browsers)

Měli byste se také seznámit s [využitím šířky pásma sítě Intune](network-bandwidth-use.md).

## <a name="intune-supported-devices"></a>Zařízení podporovaná pro Intune

Pomocí správy mobilních zařízení Intune můžete spravovat následující zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune se nedá použít ke správě operačních systémů Windows Server.

Správa zařízení Intune poskytuje [tyto funkce](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Softwarový klient pro počítače s Windows

Jako alternativní metodu registrace jde na počítače s Windows nasadit a nainstalovat [softwarového klienta Intune](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune). Softwarového klienta Intune můžete použít ke správě počítačů s Windows 7 a novějšími s výjimkou Windows 10 Home. Správa počítačů pomocí klientského softwaru přináší [tyto možnosti](windows-pc-management-capabilities-in-microsoft-intune.md).

### <a name="exchange-activesync-management"></a>Správa Exchange ActiveSync

Můžete spravovat [zařízení Exchange ActiveSync](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) z konzoly Intune. Tato možnost ve srovnání s jinými metodami poskytuje jen omezené možnosti. Seznam podporovaných zařízení najdete v článku o [možnostech integrované správy mobilních zařízení v Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0).

## <a name="intune-supported-web-browsers"></a>Podporované webové prohlížeče Intune

Různé úlohy správy vyžadují, abyste použili některý z následujících webů pro správu.

- [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konzola pro správu Microsoft Intune](https://admin.manage.microsoft.com/)

|Funkce Intune |Podporované prohlížeče|
|---------|---------|
|**Konzola správce Intune**     |  Internet Explorer 10 nebo novější<br /><br />Google Chrome (verze starší než verze 42)<br /><br />Mozilla Firefox s povoleným Silverlightem<br />**Poznámka:** Od března 2017 odebere Mozilla podporu pro Silverlight. [Přečtěte si další informace](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Portál správy Office 365**     |Všechny prohlížeče, včetně mobilních a spravovaných prohlížečů  |
|**Web Portál společnosti**     |**Na mobilních zařízeních:** používejte výchozí webový prohlížeč pro příslušnou podporovanou platformu.   <br /><br />**Na počítačích s Windows:** Internet Explorer 10 nebo novější nebo Microsoft Edge<br /><br />**Pro Mac OS X 10.9 nebo novější:** Apple Safari    |

> [!Note]
> Pro konzolu správce se nepodporuje Microsoft Edge ani mobilní prohlížeče, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Konzola Intune se z prostředí Silverlight průběžně přesouvá. Všechny funkce správy mobilních zařízení a aplikací služby Intune budou nakonec [dostupné na novém portálu Microsoft Azure Portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


K tomuto portálu se můžou přihlásit jen uživatelé, kteří mají oprávnění správce služeb nebo jsou správcem tenanta s rolí globálního správce. Abyste získali přístup ke konzole pro správu, musí mít váš účet licenci k používání Intune a stav registrace **Povoleno**.

>[!div class="step-by-step"]

>[**Práce v síti** &rarr;](network-bandwidth-use.md)  


---
title: "Porovnání možností správy počítačů s Windows"
description: "Registrace zařízení s iOSem vlastněných společností pomocí Programu registrace zařízení Apple (DEP) nebo nástroje Apple Configurator"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8f6de91724db10ef64e2c1fd6eee6101c6eac79a
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Porovnání správy počítačů s Windows jako počítačů nebo jako mobilních zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organizace mohou v Microsoft Intune spravovat počítače s Windows buď jako mobilní zařízení prostřednictvím správy mobilních zařízení (MDM), nebo jako počítače se softwarovým klientem Intune.  Microsoft zákazníkům doporučuje, aby pokud možno používali řešení pro správu MDM. Kvůli lepšímu pochopení rozdílů mezi těmito možnostmi vám nabízíme následující tabulku, která obě možnosti správy srovnává.

|**Funkce/scénář** |**Windows jako počítač**<br>softwarový klient Intune | **Windows jako mobilní zařízení**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Operační systémy** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Podpora portálu Intune** |[Konzola Silverlight](https://manage.microsoft.com)|[Azure Portal](https://portal.azure.com) |
|**Podmíněný přístup**|Není k dispozici|K dispozici <br>[Co je podmíněný přístup?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Hromadná registrace**|Není k dispozici|K dispozici <br>[Hromadná registrace zařízení s Windows](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Profily zařízení**|Není k dispozici|K dispozici <br>[Co jsou profily zařízení v Microsoft Intune?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Registrace bez agenta**|Není k dispozici |K dispozici<br>[Registrace zařízení s Windows](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Správa aktualizací softwaru**| Aktualizace Windows a aplikací od Microsoftu<br>[Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Microsoft Store pro firmy pro aktualizace Windows 10 a aktualizace aplikací od Microsoftu<br> [Konfigurace nastavení služby Windows Update pro firmy](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Správa softwarových licencí**|K dispozici <br>[Správa licenčních smluv na software počítačů s Windows](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Microsoft Store pro firmy (pouze aplikace .appx)<br>[Správa aplikací koupených z Microsoft Storu pro firmy](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventář**|K dispozici <br>[Zobrazení inventáře hardwaru a softwaru pro počítače s Windows](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|K dispozici <br>[Jak monitorovat informace o aplikacích](https://docs.microsoft.com/intune/apps-monitor)<br>[Co je správa zařízení?](https://docs.microsoft.com/intune/device-management)|
|**Zásady brány Windows Firewall**|K dispozici <br>[Pomoc při ochraně počítačů s Windows pomocí zásad brány Windows Firewall](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Není k dispozici|
|**Ochrana proti malwaru**|Funkce Endpoint Protection<br>[Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Nastavení programu Windows Defender](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Vzdálená pomoc** |TeamViewer<br>[Žádost o poskytnutí vzdálené pomoci na počítačích s Windows](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Není k dispozici |
|**Nasazení aplikací** | Není k dispozici pro Microsoft Store pro firmy,<br>jenom .exe, .appx a vícesouborové .msi<br>[Přidání aplikací pro počítače s Windows, na kterých běží softwarový klient Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|K dispozici pro aplikace z Microsoft Storu a pro podnikové aplikace<br>[Přidání aplikací pro Windows Store](https://docs.microsoft.com/intune/store-apps-windows)<br>[Přidání obchodních aplikací (LOB) pro Windows](https://docs.microsoft.com/intune/lob-apps-windows)|
|**Ochrana aplikací**|Není k dispozici|K dispozici <br>[Co jsou zásady ochrany aplikací?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Ověření stavu**|Není k dispozici|K dispozici|


### <a name="advantages-of-mdm-windows-pc-management"></a>Výhody správy počítačů s Windows v řešení MDM
Správa počítačů s Windows s využitím moderní správy mobilních zařízení přináší následující výhody:
- **Škálovatelnost** – řešení MDM je díky cloudové správě Intune škálovatelné. Softwarový klient Intune je omezený na 7000 počítačů.
- **Jednoduchost** – používá moderní funkce správy, které jsou součástí operačního systému, bez spoléhání se na staženého softwarového klienta.
- **Konzistence** – počítače s Windows se v organizaci spravují jako všechna ostatní mobilní zařízení.
<!-- - **Cloud optimization** - -->
